This is the code for http://pcapperf.appspot.com, which provides the service to analyze the web performance using the network traffic packets captured using tcpdump, WireShark, or similar tools.

PCAP files contain detailed information about the requests and
responses sent over the network. The PCAP Web Performance Analyzer
makes it easy to do web performance analysis using a PCAP file.


Using the PCAP Web Performance Analyzer, you can
  * Generate a HAR file from a PCAP file
  * Visualize the HTTP waterfall in a PCAP file using HarViewer
  * Get Page Speed suggestions for a PCAP file


We built the PCAP Web Performance Analyzer to help in analyzing mobile
web performance. Please see <a href='http://code.google.com/p/pcaphar/wiki/CaptureMobileTraffics'>how to capture mobile traffic</a> for instructions to
capture mobile traffic from your mobile device.

This project uses [pcap2har](https://github.com/andrewf/pcap2har), [dpkt](http://code.google.com/p/dpkt/) and [HarViewer](http://code.google.com/p/harviewer/).