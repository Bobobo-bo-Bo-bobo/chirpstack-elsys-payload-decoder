# Preface
Although a little more expensive as other senors, I really like the [ELSYS](https://www.elsys.se/en/) EMS/ERS sensors, especially the configuration access via NFC which simplify sensor deployment..

After the introduction of mandatory access to external packetbroker service ([The Things Stack:Packet Broker](https://www.thethingsindustries.com/docs/getting-started/packet-broker/))
the old setup using The Things Networkstack stopped working because it doesn't allow access to external networks (and I will not route internal sensor packages to third party services, especially
in light of GDPR law here in europe).

Fortunately there is [Chirpstack](https://chirpstack.io) as a viable alternative but is uses a slightly different format for payload decoding.

This payload decoder is based on the [official payload decoder](https://www.elsys.se/en/elsys-payload/) provided by the vendor for other LoRaWAN server implementations.

The decoder is based on the original payload decoder for The Things Network found at the [vendors support page](https://www.elsys.se/en/elsys-payload/).

# Using
In the Chirpstack appllication server, select the corresponding device profile in `Device-profiles` and in the `Codec` tab, select `Custom JavaScript codec functions` as `Payload codec`
and paste the content of `chirpstack-elsys-payload-decoder.js` into the box for payload decoders.

Although device configuration can be done by downlink message, a more convenient way is to use NFC to set values. Hence just paste the simple encoder function from `chirpstack-elsys-payload-encoder.js` into the encoder field.

# License
The MIT License (MIT)

Copyright © 2021 Andreas Maus <maus@ypbind.de>

Permission is hereby granted, free of charge, to any person obtaining a copy of this
software and associated documentation files (the “Software”), to deal in the Software
without restriction, including without limitation the rights to use, copy, modify, merge,
publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons
to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or
substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR
PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE
FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

