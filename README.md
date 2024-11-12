# What is this?

version 1:
I quickly completed the ping part which was an exercise in the first version because it is similar to udp. I made progress in multithreading but now I am getting a strange error:
it seems to be a problem with socket usage, I am working on it.

➜  NetworkApplications sudo python3 NetworkApplicationsSrcFinal.py mtroute -p icmp uni-leipzig.de

Password:
Exception in thread Thread-1 (send_probes):
Exception in thread Thread-2 (receive_responses):
Traceback (most recent call last):
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/threading.py", line 1052, in _bootstrap_inner
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/threading.py", line 1052, in _bootstrap_inner
    self.run()
    self.run()
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/threading.py", line 989, in run
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/threading.py", line 989, in run
    self._target(*self._args, **self._kwargs)
  File "/Users/mustafacaglar/PycharmProjects/NetworkApplications/NetworkApplicationsSrcFinal.py", line 639, in receive_responses
    self._target(*self._args, **self._kwargs)
  File "/Users/mustafacaglar/PycharmProjects/NetworkApplications/NetworkApplicationsSrcFinal.py", line 611, in send_probes
    trReplyPacket, hopAddr, timeRecvd = self.receiveOneTraceRouteResponse()
                                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    timeSent = self.sendOnePing(destinationAddress, packetID, seq_num, ttl, dataLength=52)
  File "/Users/mustafacaglar/PycharmProjects/NetworkApplications/NetworkApplicationsSrcFinal.py", line 534, in receiveOneTraceRouteResponse
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Users/mustafacaglar/PycharmProjects/NetworkApplications/NetworkApplicationsSrcFinal.py", line 297, in sendOnePing
    pkt, addr = self.icmpSocket.recvfrom(MAX_DATA_RECV)
                ^^^^^^^^^^^^^^^
AttributeError: 'MultiThreadedTraceRoute' object has no attribute 'icmpSocket'
    self.icmpSocket.setsockopt(socket.SOL_IP, socket.IP_TTL, ttl)
    ^^^^^^^^^^^^^^^
AttributeError: 'MultiThreadedTraceRoute' object has no attribute 'icmpSocket'

one of the errors I get is like this