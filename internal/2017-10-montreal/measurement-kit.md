# Measurement-Kit (MK)

Simone will be working on an OTF fellowship and the hosting organization is M-Lab.

The fact that M-Lab is the hosting organization is an opportunity for collaborating on things related to performance.

By having M-Lab as the host organization, measurement-kit can have a broader scope beyond OONI.

During this year, we would like to reach MK 1.0.0 ---> function required to implement the apps.

## Things to do

1. Add Windows support to MK

2. Improvements of the NDT client inside of MK (this is important since some ports used by NDT are filtered)

3. Low level data gathering (mainly TCP info, but maybe also other things)

   TCP BBR --> MK will probably be one of the clients to experiment with this

4. Improvements of existing engines

	* Add support for HTTP2 (will use existing libraries)

	* Integrate c-ares as a DNS engine (will enable to craft and send our own packets, so very low level)

	* Possibility to collect the TLS Hello (initial handshake of TLS) -- we need it to understand if there is SNI censorship

	* Better traceroute engine

5. Rapid response measurements (engine that you can give it information to trigger tests depending on what is needed) -- Modify the engine of Glasnost

6. Support follow-up measuremnts (identifies follow-up measurements, there was rought consensus on putting the logic inside of MK rather than outside it &mdash; i.e. internal rather than external DSL?)

