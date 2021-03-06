## JitterTrap

<a href="https://scan.coverity.com/projects/4088">
  <img alt="Coverity Scan Build Status"
       src="https://scan.coverity.com/projects/4088/badge.svg"/>
</a>
[![Build Status](https://travis-ci.org/acooks/jittertrap.svg)](https://travis-ci.org/acooks/jittertrap)
[![Code Climate](https://codeclimate.com/github/acooks/jittertrap/badges/gpa.svg)](https://codeclimate.com/github/acooks/jittertrap)

JitterTrap is a network measurement and impairment tool for developers of real-time applications and devices.

It has two broad areas of use:
* detection and measurement of unexpected delays, introduced by the device or application under test. That is, characterising the source behaviour with respect to throughput, packet rates, jitter.
* introducing and controling known network impairment conditions (eg. delay, jitter, packet loss) to verify the correct operation of the device or application under test. That is, characterising the behaviour of the destination, with respect to delay, jitter and loss.

The user interface is implemented as a web application.  
![JitterTrap UI](/docs/screenshots/jittertrap-20150527.png?raw=true "JitterTrap Interface")

## Building JitterTrap
### Dependencies
* libnl >= 3.2.24

#### Fedora  
Build dependencies  
`$ sudo yum install libnl3`  
Run-time dependencies:  
`$ sudo yum install libnl3-devel`

#### Ubuntu  
Build dependencies:  
`$ sudo apt-get install libnl-3-dev libnl-route-3-dev libnl-genl-3-dev`  
Run-time dependencies:  
`$ sudo apt-get install libnl-3-200 libnl-route-3-200 libnl-genl-3-200`

#### Slackware  
If you installed packages from 'l' series then libnl is already installed.  
Check version with:  
`# slackpkg search libnl`

### Compiling JitterTrap

Fetch:  
`$ git clone https://github.com/acooks/jittertrap.git`  

Build:  
`$ cd jittertrap`  
`$ make WEB_SERVER_DOCUMENT_ROOT=$(pwd)/frontend/output`

Run:  
`$ sudo backend/jittertrap`

Note:
By default, Jittertrap listens on port 80. To adjust this to your desired port, you need to set WEB_SEVER_PORT when building.
E.g.
`$ make WEB_SERVER_DOCUMENT_ROOT=$(pwd)/frontend/output WEB_SERVER_PORT=8000`

