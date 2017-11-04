# echacks2017
My work from Electric City hacks 2017

# Project

The goal is to create a VR controller that has real-time 6DOF inside-out tracking, which interfaces to a web application.

The controller is a Raspberry Pi Zero W, with a Raspberry Pi Camera 1.3 module, running a positional tracking library from the Robotics and Perception Group at ETH Zurich

# Components

### VR Controller

The Raspberry Pi is connected to a laptop via a micro-usb ethernet hack, such that it provides power and a way of transferring data.

The positional tracking is done through a method called "semi-direct visual odometry" to give 6DOF to the controller in semi real time.

It then transmits the data over the ethernet connection by writing stdout on a ssh connection.

### Controller Server

On the laptopt to which the controller is connected, a server is running that reads the output from the controller over ssh and pushes it to a socket.

### Web Application (VR/AR)

The web app has an interface for reading the values from the port, and therefore is able to read the tracking information from the controller. This is implemented in a simple front-end interface.
