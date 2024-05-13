#### novachat-engine-android

Building novachat-engine-android use Telegram android[Telegram](https://github.com/DrKLO/Telegram)

    git clone https://github.com/DrKLO/Telegram --recurse-submodules -b release-7.3.0_2206




Modify:


    file: Handshake.cpp:processHandshakeResponse

    serverPublicKeys.push_back("-----BEGIN RSA PUBLIC KEY-----\n"
                           "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAk+8JrmdodExqA7MDGrSp\n"
                           "0yQ+tVKgjDgDqXog2dp++b2l8VlK3/yXHuQuYuoESQ9yloPKb64sLa++4LO2itv5\n"
                           "R7Q4ByKdr4cEDeO7grK5uaDH8qYfG71twBxcubP18OFuciMMhqCsmSPmpeajeJ6S\n"
                           "wli7NMzD6isi2IXOAxVKeFkzyo+aQ6rtiA9UImLVCRWMKmtANT24qCleXuvN4lo/\n"
                           "m2cjSpHMLnZSPROS//Zvst5WRht2qGO8DAI8Vm0ZVgH7EXHweojWBPsvjVt/yEKl\n"
                           "lKzWyPFnE1vUfN/47OaXGfJdZ3v4tjZN8OgcUUoXjnJiOHkF8k9Qj9agGaOqIWeJ\n"
                           "qQIDAQAB\n"
                           "-----END RSA PUBLIC KEY-----");
    serverPublicKeysFingerprints.push_back(0x1234567890123456LL);

    to:

     serverPublicKeys.push_back( "-----BEGIN RSA PUBLIC KEY-----\n"
                        "MIIBCgKCAQEArPiEA6JTgNjNPjzSErNFMwANLcdkD+aU8pTjp620bMBzUV4aWJmR\n"
                        "lA2oddA4jc9Lej0Y6pvGZwWVl2lsMXB1Fe1P6YiTjj2Iz5X+gfLmbkiqZc6mxon+\n"
                        "QrYK87qPBwJ8FzBVBg0LxVwMsNj7uXv1wlCXDeM8ANXMULLa6SZe3QL1mG0Ys2+R\n"
                        "NXns3EnLKeukHWSofYh3jMDNe2zw4xlxSROP1HXF7OMZ2S4CKDy9jcecq+CHVAxb\n"
                        "T+pJp0mmV6vzGkaP+VP3Gg8c+FraWJrB8FcYtDGRHCLwL5ubArQeTufWs+56qqDO\n"
                        "1Lx1CK42dFlTopPrAj3Evb5MATmU9ggl8wIDAQAB\n"
                        "-----END RSA PUBLIC KEY-----\n");
    serverPublicKeysFingerprints.push_back(10919150075863652644LL);


    file: ConnectionsManager.cpp:initDatacenters

    datacenter->addAddressAndPort("YOUR IP", YOUR PORT, 0, "");

    modify all, default 5 dc ip to the same one


