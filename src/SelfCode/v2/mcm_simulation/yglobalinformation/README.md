>其实如果你想进行shoreside与vehicle之间，vehicle与vehicle之间的通信的话，只需要去配置uFldNodeBroker和uFldShoreBroker即可。在二者的配置块中去写src和alias。    

>>首先说uFldNodeBroke的src和alias。所谓的src就是所有在本community下的发送到MOOSDB的变量都可以作为src，也就是src应该是由application发送的或者是由行为发送的MOOSDB变量。而alias就是在src中配置的变量会以alias中配置的名字发送到shoreside，也就是说你通过这样的配置让vehicle community中的变量（src的值）以另一个名字（alias的值）发送给了shoreside端。这样就完成了从vehicle到shoreside 的连接。    

>然后说uFldBroker。它的作用就是把它自己community中的MOOS变量（src值）以另一个名字（alise值）发送，让每个航行器都能够接收到。    

综上，就可以建立起整个系统的通信。对于vehicle和vehicle之间，可以在shoreside端建立application去转发信息。如在deallocation_for_yAllocation中所使用的yGlobalInformation工具（自己写的)。
