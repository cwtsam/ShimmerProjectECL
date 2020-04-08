# ShimmerProjectECL is a java-based project to make a simple data streaming software for Shimmer biopotential signal sensor using LSL (Lab Streaming Layer) protocol.
## Designed for the Windows platform, Shimmer GSR+ sensor.

Based on the [ShimmerEngineering's repo](https://github.com/ShimmerEngineering/ShimmerJavaExamples)

## Original Description for the repo
There are a number of examples
- ECGToHRExample

  _Shows how to retieve data from the ObjectCluster (see ShimmerPC.MSG_IDENTIFIER_DATA_PACKET) as well how to use the ECG to Hear Rate Algorithm._
  
- PPGToHRExample

  _Shows how to retieve data from the ObjectCluster (see ShimmerPC.MSG_IDENTIFIER_DATA_PACKET) as well how to use the PPG to Hear Rate Algorithm._

- SensorMapsExample

  _Shows how to configure a Shimmer device via a User Interface while it is connected._

- ShimmerSetupExample

  _Shows how to configure a Shimmer device via the constructor._

For Shimmer2R uses please refer to the legacy example


# License
follow the original license

# how to use "ApplicationShimmer"
1. Install Java Development Kit 1.8
2. Clone this repo to local and open it with Eclipse Java IDE (import as a Gradle Project, right click on Package Explorer window and click "Import..." > Gradle > Existing Gradle Project).
3. Resolve all issues and clean project before building. (Project > Clean...) 
4. Under "ecl" directory, select "ApplicationShimmer.java" and build it (Path should be /ShimmerBasicExamples/src/main/java/ecl/ApplicationShimmer.java). 
5. Once built, we want to make it into a runnable java file. Right-click on "ApplicationShimmer.java" and then "Export...". Export as Java > Runnable JAR file.
6. Pair your Shimmer GSR+ sensor to your PC by bluetooth connection.
7. Check the port number (i.e. COM6) for your Shimmer sensor on your PC.
8. Run the compiled "ApplicationShimmer.jar" in Eclipse IDE or by typing `java -jar ApplicationShimmer.jar` in powershell.
9. Type in the port number in the app and you'll see connection log and sensor data.

## Editing sampling rate
For my project, I require sampling and streaming at 256 Hz instead of 128 Hz. ShimmerGSR allows you to modify the sampling rate streaming via bluetooth. I would then need to stream it at 256 Hz on LSL.
1. In "ApplicationShimmer.java", find the line "final static double kSamplingRate = 128;" Update it to 256 or your preferred sampling rate.
2. Download "ConsensysBASIC" should be free https://www.shimmersensing.com/products/consensys
3. In Consensys, go to manage devices, connect your Shimmer via the dock.
4. Write firmware and configuration to 256 Hz.
5. Build and run the modified JAR file. (Steps 5 to 9 above)

