# NS3-SUMO-CONTROL

Thanks to vodafone-chair's work:[ns3-smo-coupling](https://github.com/vodafone-chair/ns3-sumo-coupling), it's easy for us to focus on the logic of service.

## How To Build?

The test environment is SUMO(>=1.0.0) and NS3.26 . SUMO's Traci changed from the version 1.0.0, so it is recommended to use the after version.

Move the "traci" and "traci-applications" two directories into the ns3/src and build like new module.

Config files of sumo are in traci/examples/XX-simple.

## How to Run?
reconfigure ns3 like this:

- "CXXFLAGS="-std=c++11" ./waf configure --disable-tests --disable-examples --disable-python"
- "./waf build"
- And then try to run the test file in the scratch.

how to run in the scratch, followings will help:

- Move the test file to the "ns3/scratch/" directory : "cp src/traci-applications/examples/line-test.cc scratch/"
- Enter the scratch directory: " cd scratch"
- Run: "../waf --run line-test"

## What can do?

1. You can add or change apis in `traci-applications/model/sumo-ns3-control-util.h`  to control sumo, such as get car(in sumo)'s information or change their speeds.

2. You can add or change callback function in `traci-appications/model/sumo-ns3-control-util.h`, and bind some services logic to the callback function. Such as, find   an event happened in sumo, I can handle this event in ns3 by sending messages, or do some tricks..... 