# MK knowledge share

Knowledge sharing on MK. Attendees: sbs, darkk, and landers.

- C++ standard: we're currently using C++14, which enables to do cool
  things with lambda captures, but we may possibly return to C++11, since
  we may want to support more old systems.

- Another possibility for supporting old systems is to build also
  the compiler and libc++ (i.e. a fully backport) aiming to produce
  libraries and possibly also a static binary.

- The two C++11 (and hence C++14) features that we use the most are
  lambda functions and smart pointers.

- We created a wrapper for `std::shared_ptr`, called initially `Var` and
  now `SharedPtr` that throws when the underlying pointer is `nullptr`.

- Of course, one SHOULD NOT dereference an empty pointer, but we may
  refactor the code and don't notice (especially when we are using
  heavily move semantic), so we decided to add this extra safety layer.

- With C++14 we heavily use the pattern where we're initializing
  variables in the lambda capture, specifically moving inside the
  lambda capture variables not needed outside.

- With C++11 the pattern is simpler: we store all what we need inside
  a struct managed through a shared pointer and we use `[=]`.

- We generally avoid using objects for async operations and we use
  instead smart pointers to structs and functions. This way, we
  make sure that an async operation has ownership of a data structure
  as long as it is pending.

- The three objects that require shared ownership are:

    - The I/O loop, which should be shared across many objects
    
    - The logger
    
    - a TCP-like connection (so that we can have a pending read and a
      pending write concurrently running)
 
 - Allowing a pending read and a pending write concurrently running is useful,
   e.g., if we want to emulate BitTorrent and for middleboxes that may send
   us blockpages before we even start sending a request.
 
 - Decoupling classes or structures and the pointer modifier is good when
   you want to give their user a choice. Otherwise, when you want to enforce
   a specific sharing (or non sharing) pattern, it is better to write a
   wrapper class (and perhaps call it `FooPtr` rather than `Foo`).
