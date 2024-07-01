^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package odri_master_board_sdk
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1.0.7 (2024-06-24)
------------------
* Fix header to have the package working on Noble (@olivier-stasse)
* Fix building Python bindings on Mac (@ManifoldFR)
* Remove fetching Catch2 v3 and detect automatically the installed version. (@olivier-stasse)
* Add Rolling github action (@olivier-stasse)
  
1.0.6 (2023-11-15)
------------------
* Makes cmake-format happy !
* [CMakeList.txt] Fix CMakeLists.txt to install the header.
* Add cmake-format.
* Change name of the package to make it release in ROS-2.
* CMake: update submodule use
* CMake: bump catch2
* Partial support of the new Power-Board hardware
* Fix two bugs (FLOAT_TO_D8QN and compiling issue) + remove warnings on the core library.
* [master_board_sdk] Fix compilation error on master_board_interface.cpp l.263
  Introduced by commit 782c348 it fails because %s is expecting char * and not std::string.
  This fails on clang.
* [master_board_sdk] Fix warnings.
  There are still some warnings wih Catch2 and clang.
  But Catch2 is a dependency and should be fixed upstream.
* [protocol] FLOAT_TO_D8QN has a wrong bracket. This commit fix this.
* [cmake] Synchronize to remove error during install process.
* Add error, thrown by sdk, for protocol version mismatch (during init)
* Add ament_cmake build_type export in package.xml and install package.xml file
* Update sdk/master_board_sdk/CMakeLists.txt
* [master_board_sdk/CMakeLists.txt] Remove useless CMAKE_PREFIX_INSTALL specification.
* [master_board_sdk/package.xml] Remove ament_cmake dependency and buildtool dependency.
* [CMakeLists.txt] Remove dependency to ament_cmake and generates files for Colcon underlays.
* [package.xml] Add dependence to ament_cmake if ROS-2 is detected.
* [CMakeLists.txt] Uses ROS-2 if the environment is compatible.
* [package.xml] Add ament_cmake export for colcon support.
* [cmake] Add install procedure for file package.xml
* Adding ROS-2 rolling CI to the repository and some changes to have it working.
* [sdk/master_board_sdk/tests/test_protocol.cpp] Commented the test on NaN which is failing.
* [sdk/master_board_sdk/package.xml] Fix package dependency.
  Update version to 3.
  Add dependencies to libboost-python.
  Add git for dependencies.
* [cmake/sdk_master_board/CMakeLists.txt] Improve CMakeLists.txt.
* [cmake/master_board_sdk/CMakeLists.txt] Removing components
* [cmake] Change again python detection place.
* [cmake] Change place for python detection
* [sdk/master_board_sdk/CMakeLists.txt] Update Find Python detection.
  Update message when detection is failing.
* [Cmake] remove python components.
* [master_board_sdk/CMakeLists.txt] Provides better Python detection
* [cmake] Synchronize
* [package.xml] XML version 1.0
* [package.xml] Remove Boost depend.
* Cmake
* pre-commit run -a
* sync submodule
* (Small) Fix for sdk examples with python >=3.8
* Apple support for wired connection.
* [Link_manager] Fix message when the priority is not set correctly and fails using assert.
* [cmake] Switch back the default to ON if this is not an APPLE platform
* Add Python bindings for SetKp/Kd/SaturationCurrent and fix example.py
* Zero-initialise all members of Motor
* Change macro name for platform from UNIX to linux.
  Include net/if_arp.h only for APPLE.
* Fix missing header.
* Fix wrong elif condition and missing brackets.
* Apple support for wired connection.
* example.py: Initialise all reference values and gains to zero
  This should not really be needed anymore since values are already
  zero-initialised in `Motor` but better be safe than sorry.
* fix example.py: time.clock() has been removed
  `time.clock()` has been deprecated in Python 3.3 and does not exist
  anymore in newer versions.  Use `perf_counter` instead.
* Add Python bindings for Motor::SetKp/Kd/SaturationCurrent
  At least by now they are implemented in motor.cpp, so there's no reason
  to not add bindings for them.
* Zero-initialise all members of Motor
  This should fix an issue that was likely caused by `kp` being set to
  some random non-zero value, resulting in the motor unintentionally being
  held at some position.
* Missing include
* plateform and distro modules optionnal for sdk example com_analyser.py
* Swap process_time and clock for better intelligibility
* Protocol version added in init_ack packet & version mismatch throw runtime error in sdk
* Fix sdk examples for python version >=3.8
* CMake: add unit tests
* Fix minor build error and update cmake submodule
* CMake: add unit tests
* Handle out-of-range motor params without wraparound (`#117 <https://github.com/olivier-stasse/master-board/issues/117>`_)
  Avoid fixed-point overflow
* Minor CMakelist change and cmake update
* SDK: fix a few warnings
* [CMake] set RPATH for executables
* SDK: fix warnings
* Add Python bindings for powerboard data
* add pyton bindings for power baord
* [SDK][Firmware] Add partial support for power-board, Update protocol version and sdk accordingly
* Contributors: EtienneAr, Felix Kloss, Guilhem Saurel, Naveau, Olivier Stasse, Thomas Flayols, Trevor Blackwell, odri, thomasfla

1.0.5 (2022-06-30)
------------------
* Merge pull request `#110 <https://github.com/olivier-stasse/master-board/issues/110>`_ from open-dynamic-robot-initiative/fwidmaier/version
  Bump version to 1.0.5 and add changelog
* Bump version to 1.0.5 and add changelog
* fix package.xml for catkin build compatibility
* Merge pull request `#109 <https://github.com/olivier-stasse/master-board/issues/109>`_ from open-dynamic-robot-initiative/jviereck/mailbox_only
  Use mailbox for SPI communication
* fix example_imu_data_collection
* Add MasterBoardInterface::get_imu_data()
  Add method to easily get the full IMU data.
* Adding CMakeList entry for new example
* Adding example for collecting and plotting IMU data for 10 seconds
* SDK: cherry-pick fixes, fix `#106 <https://github.com/olivier-stasse/master-board/issues/106>`_
  initial commit: 32b0252c64a064c55e8cd07115a003b15c0d0a86
* Contributors: Felix Widmaier, Guilhem Saurel, Julian Viereck, Maximilien Naveau

1.0.4 (2021-07-21)
------------------
* Merge pull request `#99 <https://github.com/olivier-stasse/master-board/issues/99>`_ from paLeziart/add-parse-sensor-data
  Add parse sensor data
* Add comment to explain the call to ParseSensorData
* Add a ParseSensorData in MasterBoardInterface Init function
* Merge pull request `#97 <https://github.com/olivier-stasse/master-board/issues/97>`_ from open-dynamic-robot-initiative/jviereck/fix_regression
  Fix problem with reference to packed fields in MasterBoardInterface ParseSensorData
* Fix problem with reference to packed fields in MasterBoardInterface::ParseSensorData
* Merge pull request `#94 <https://github.com/olivier-stasse/master-board/issues/94>`_ from open-dynamic-robot-initiative/jviereck/fix92
  Set close to zero velocity to zero. Fixes `#92 <https://github.com/olivier-stasse/master-board/issues/92>`_
* Address review comments
* Set close to zero velocity to zero. Fixes `#92 <https://github.com/olivier-stasse/master-board/issues/92>`_
* Contributors: Julian Viereck, odri, paLeziart

1.0.3 (2021-06-09)
------------------
* Merge pull request `#90 <https://github.com/olivier-stasse/master-board/issues/90>`_ from open-dynamic-robot-initiative/mnaveau/python_bindings_by_default
  Update CMakeLists.txt
* Update CMakeLists.txt
* Contributors: Naveau

1.0.2 (2021-05-11)
------------------

1.0.1 (2021-04-16)
------------------
* Merge pull request `#82 <https://github.com/olivier-stasse/master-board/issues/82>`_ from open-dynamic-robot-initiative/jviereck/attempt_three
  Make communication more robust
* Increase the CONFIG_SPI_N_ATTEMPT from 2 to 3. Add a counter in the example to see number of times an error was reported
* Merge pull request `#78 <https://github.com/olivier-stasse/master-board/issues/78>`_ from open-dynamic-robot-initiative/mnaveau/missing_definition
  [sdk] fix missing definition from the Motor class
* Merge pull request `#77 <https://github.com/olivier-stasse/master-board/issues/77>`_ from open-dynamic-robot-initiative/jviereck/error_encoder_2
  SDK: Adding error code for encoder2 error
* Merge pull request `#75 <https://github.com/olivier-stasse/master-board/issues/75>`_ from open-dynamic-robot-initiative/mbogdanovic/fix_stat_overflow
  SDK: Fix bug/crash with overflow in statistic computation
* [sdk] fix missing definition from the Motor class
* SDK: Adding error code for encoder2 error
* Update README.md
* Update README.md
* SDK: Fix bug/crash with overflow in statistic computation
* Merge pull request `#72 <https://github.com/olivier-stasse/master-board/issues/72>`_ from open-dynamic-robot-initiative/mnaveau/export_library
  Warning Hunt and CMake export.
* update target names
* update the interface to double values
* remove warning in the example_pd
* fix a couple of warnings
* Synchronize.
* export the includes and install them
* fix project name
* add Boost to the package.xml
* add the license and package.xml
* export the cmake library
* Merge pull request `#74 <https://github.com/olivier-stasse/master-board/issues/74>`_ from open-dynamic-robot-initiative/jviereck/current_sat
  [SDK] Add support for current saturation
* [SDK] Add support for current saturation
* Merge pull request `#71 <https://github.com/olivier-stasse/master-board/issues/71>`_ from thomasfla/master
  Add local joint impedance control interface + improve python binding packaging
* Merge pull request `#1 <https://github.com/olivier-stasse/master-board/issues/1>`_ from nim65s/master
  Update CMake
* CMake: ensure python lib always find c++ lib
* CMake: fix sdk installation path, fix `#45 <https://github.com/olivier-stasse/master-board/issues/45>`_
* CMake: update submodule and its use
* Tune data representation in the protocol for usefull gains levels, Fix conevrsion of Kp Kd
* Add IQ scalling for Kp and Kd values
* Merge pull request `#66 <https://github.com/olivier-stasse/master-board/issues/66>`_ from maximekli/internship-major-refactor
  [Firmware][SDK][Doc] Major refactor and protocol update;
* Merge pull request `#19 <https://github.com/olivier-stasse/master-board/issues/19>`_ from AlexisPotier/communication
  Fixed overflow issue in com analyser script
* Fixed overflow issue on com_analyser
* Plot graphs even if the script is stopped by a master board timeout
* Merge pull request `#17 <https://github.com/olivier-stasse/master-board/issues/17>`_ from AlexisPotier/communication
  Better way to get wifi channel
* Better way to get wifi channel
* Removed listener mode special case because mb does not send packets in waiting for init anymore
* Merge pull request `#3 <https://github.com/olivier-stasse/master-board/issues/3>`_ from maximekli/master
  Update fork
* Merge pull request `#15 <https://github.com/olivier-stasse/master-board/issues/15>`_ from AlexisPotier/communication
  Added communication analyser script to test the network link between PC and MB + channel 14 support
* Small refactor
* Replaced latency script by communication analyser script
* Added getters for wifi channel and protocol version
* Enable channel 14 for wifi communication
* Merge pull request `#2 <https://github.com/olivier-stasse/master-board/issues/2>`_ from maximekli/master
  Update fork
* Merge branch 'AlexisPotier-print'
* Merge branch 'print' of https://github.com/AlexisPotier/master-board into AlexisPotier-print + some formatting
* Avoid displaying headers when there is no spi connected
* Merged PrintCmdStats and PrintSensorStats, improved the display of wifi/eth stats
* Improved the display of IMU, ADC and motors data
* Revert "Changing scheduler param to realtime in examples"
  This reverts commit beead35848bc759a2ef147b0a68dc79b47e57f74.
* Improving display of latency test result
* Changed protocol version from 2 to 3
* Merge pull request `#13 <https://github.com/olivier-stasse/master-board/issues/13>`_ from AlexisPotier/latency
  Latency script for network link into master branch
* Changing scheduler param to realtime in examples
* Documentation update : added informations about the latency calculator script
* Creation of a python script to compute the latency of the wifi/ethernet communication
* Changed the protocol to be able to compute the latency for ethernet/wifi communication
* Initialization of pointer + extra safety when stopping the interface
* Added member function to check if driver is enabled
* Fix division by zero
* git push origin masterMerge branch 'AlexisPotier-master'
* Merge branch 'master' of https://github.com/AlexisPotier/master-board into AlexisPotier-master
* Fix for command loss feedback reset and overflow
* Get first packet loss to avoid jump in value
* Proper getter and setters for a few driver properties
* git push origin masterMerge branch 'maximekli-master'
* Merge branch 'master' of https://github.com/maximekli/master-board into maximekli-master
* Merge branch 'memory_leaks'
* Merge branch 'signal_handler'
* Small fixes after merge
* git push origin masterMerge branch 'AlexisPotier-signal_handler'
* Merge branch 'signal_handler' of https://github.com/AlexisPotier/master-board into AlexisPotier-signal_handler
* git push origin masterMerge branch 'AlexisPotier-memory_leaks'
* Merge branch 'memory_leaks' of https://github.com/AlexisPotier/master-board into AlexisPotier-memory_leaks
* Small refactor when checking drivers
* Free link_handler when the program is stopped by SIGINT signal
* Removed "virtual" keyword for stop function in ESPNOW_manager
* Close correctly the pthread to avoid memory leaks
* Added destructors in the interface to close correctly link_handler\_ and avoid memory leaks
* Small refactor
* Added extra safety when closing interface
* Merge pull request `#5 <https://github.com/olivier-stasse/master-board/issues/5>`_ from AlexisPotier/master
  Fix seg fault on stopping the interface
* Added default argument for listener mode in interface constructor
* Handling Keyboard Interrupt signal to close threads correctly when the script is interrupted by the user
* Update doc with listener example
* Updated outdated doc
* Added connected status as an attribute in motor_driver class and adapting interface and example with it
* Small refactor
* Rework for listener to work in more cases
  Added getters for session id and reset packet loss stats method
* Override stop method to stop differently wifi and ethernet connexions
* Initialization of bpf in ESPNOW_manager
* Small refactor on shutting down the interface
* Little fix
* Merge branch 'feedback_on_packet_loss'
* Merge branch 'AlexisPotier-feedback_on_packet_loss'
* Merge branch 'feedback_on_packet_loss' of https://github.com/AlexisPotier/master-board into AlexisPotier-feedback_on_packet_loss
* Added getters for feedback and changed stats print functions
* Created listener script that gathers sensor data from any connected mb
* Adapted both examples for the new listener mode
* Added listener mode to the interface that allows to get sensor data from any running mb (no session id checking)
* Updated python example with failed spi transactions support
* Added failed spi transactions support to example
* Added protocol version to init msgs in interface
* Updating interface and examples with the connected spi slaves feedback
* Removed state machine test example
* Fixed the error (invalid pointer) occurring at the end of the example
* Fixed the segmentation fault occurring at the end of the example
* Merge branch 'AlexisPotier-new_branch'
* Merge branch 'new_branch' of https://github.com/AlexisPotier/master-board into AlexisPotier-new_branch
* Giving feedback on packet loss
* update files to merge
* update feedback packet loss using latest version
* Merge branch 'master' of https://github.com/open-dynamic-robot-initiative/master-board
* Merge pull request `#62 <https://github.com/olivier-stasse/master-board/issues/62>`_ from open-dynamic-robot-initiative/fwidmaier/fix-clang-error
  Using constant value for array length
* Using constant value for array length
  Using the value from `this->bpf.len` for defining the array length seems
  to be accepted by GCC but resulted in an error with clang.  Therefore
  store the value to a constexpr and use that instead.
* Merge branch 'master' of https://github.com/AlexisPotier/master-board
* add feedback on packet loss
* Merge pull request `#59 <https://github.com/olivier-stasse/master-board/issues/59>`_ from AlexisPotier/master
  Added setcap solution in the SDK documentation and fixed a problem with the images in the SPI documentation
* Update README.md
* Adapting the examples for the new interface timeout (while waiting for acknowledgment)
* Adding a new timeout to the interface in order to shut it down if we wait for an acknowledgment msg for too long
* Added session id handling in sdk interface
* Moving the master board state machine test program to its own folder and editing the CMakeLists and README files to run it
* New python test file in the sdk to demonstrate every state of the master board state machine
* Adapting python example for use with new master board state machine. Runs ok but seg fault in the end while stoping interface.
* Adapting python master board sdk for use with new state machine
* Small change to match previous commit
* Small method name change to be more consistent with previous code
* Adapting the example for use with the new master board firmware that uses init messages
* Adapting master board interface for the new masterboard firmware that uses init messages. Not adapted for use with python.
* Merge pull request `#55 <https://github.com/olivier-stasse/master-board/issues/55>`_ from open-dynamic-robot-initiative/jviereck/link_manager_destruct
  LinkManager: Close connection on destruction
* LinkManager: Close connection on destruction
* Merge pull request `#52 <https://github.com/olivier-stasse/master-board/issues/52>`_ from thomasfla/fix_linacc
  [sdk] rescale linear acceleration to SI, fix typo in python bindings
* [sdk] rescale linear acceleration to SI, fix typo in python bindings
* Merge pull request `#35 <https://github.com/olivier-stasse/master-board/issues/35>`_ from paLeziart/guide_python_script
  [SDK] Small guide on how to compile and launch the Python example
* Merge pull request `#50 <https://github.com/olivier-stasse/master-board/issues/50>`_ from thomasfla/encoders_offset
  [SDK] Add a settable offset on position reading and reference positio…
* Merge pull request `#49 <https://github.com/olivier-stasse/master-board/issues/49>`_ from open-dynamic-robot-initiative/mnaveau/timeout_send_command
  Timeout of the SendCommand only after the first command
* Update the timeout of the SendCommand only after the first command as been set.
* [SDK] Small guide on how to compile and launch the Python example
* [SDK] Add a settable offset on position reading and reference position. Usefull for encoder offset calibration routines
* Merge pull request `#46 <https://github.com/olivier-stasse/master-board/issues/46>`_ from thomasfla/tflayols_devel
  [SDK] [Firmware] Expose estimated linear acceleration from IMU
* [SDK] expose accelerations in m/s^2 instead of g
* [Firmware][SDK] Configure IMU to send linear acceleration estimate, adapt protocol and sdk to read it. Warning! Protocol has changed, the Master board needs to be flashed
* [SDK] Remove N_SLAVE_CONTROLED from the library, use it only in the example; Set default value to 1
* Merge pull request `#34 <https://github.com/olivier-stasse/master-board/issues/34>`_ from nim65s/master
  [Python] replace getopt by argparse
* Merge pull request `#40 <https://github.com/olivier-stasse/master-board/issues/40>`_ from nim65s/cmake
  [CMake] PKG_CONFIG_APPEND_BOOST_LIBS has been fixed
* Merge pull request `#42 <https://github.com/olivier-stasse/master-board/issues/42>`_ from open-dynamic-robot-initiative/jviereck/si_velocity_example_py_followup
  Update example.py as for d gain si unites
* Update example.py as followup to `#39 <https://github.com/olivier-stasse/master-board/issues/39>`_.
* Merge pull request `#39 <https://github.com/olivier-stasse/master-board/issues/39>`_ from open-dynamic-robot-initiative/jviereck/fix38_si_velocity
  [sdk] Fix velocity si unit conversion. Fixes `#38 <https://github.com/olivier-stasse/master-board/issues/38>`_
* [CMake] PKG_CONFIG_APPEND_BOOST_LIBS has been fixed
* [Python] replace getopt by argparse
  Which is cleaner, and comes with more functionnalities
* [Python] avoid lines > 120 chars
* [sdk] Fix velocity si unit conversion. Fixes `#38 <https://github.com/olivier-stasse/master-board/issues/38>`_
* Merge pull request `#36 <https://github.com/olivier-stasse/master-board/issues/36>`_ from paLeziart/fix_typos_connection
  [SDK] Fix typos: connection instead of connexion
* [SDK] Fix typos: connection instead of connexion
* Merge pull request `#33 <https://github.com/olivier-stasse/master-board/issues/33>`_ from nim65s/master
  [CMake] clean master_board_sdk
* [CMake] PKG_CONFIG_APPEND_BOOST_LIBS doesn't work with boost python for now
* [CMake] typo
* [CMake] build python example
* [CMake] sync submodule
* remove symlinks
  build directory could be anywhere
* [CMake] python .pc is configured in scrcpy/
* [CMake] build python .so in standard place
* [CMake] install python .so in PYTHON_SITELIB
  - CMAKE_INSTALL_PREFIX is implied
  - PROJECT_NAME has dashes, so this can't work with python import system
* [CMake] boost python is required for python
* [CMake] update project definition
* [CMake] remove end-of-line spaces
* Merge pull request `#29 <https://github.com/olivier-stasse/master-board/issues/29>`_ from paLeziart/IMU_bindings
  [SDK] Python bindings for IMU data (accelerometer, gyroscope, attitude)
* Merge pull request `#30 <https://github.com/olivier-stasse/master-board/issues/30>`_ from paLeziart/shutdown-timeout
  [SDK] Timeout of MasterBoardInterface if the master board is not resp…
* [SDK] Timeout of MasterBoardInterface if the master board is not responding
* [SDK] Python bindings for IMU data (accelerometer, gyroscope, attitude)
* Merge pull request `#26 <https://github.com/olivier-stasse/master-board/issues/26>`_ from open-dynamic-robot-initiative/tflayols_devel
  [Firmware] Fix the IMU driver to deal with combined messages from IMU …
* [sdk] fix makefile
* Merge pull request `#25 <https://github.com/olivier-stasse/master-board/issues/25>`_ from paLeziart/bindings_adc_and_gains
  [SDK] Adapting gains for SI units + Python bindings for adc property …
* [SDK] Adapting gains for SI units + Python bindings for adc property and printADC function
* Merge pull request `#20 <https://github.com/olivier-stasse/master-board/issues/20>`_ from paLeziart/noprintf
  [SDK] Option to have no printf when running on realtime loop
* [SDK] Option to have no printf when running on realtime loop
* Merge pull request `#9 <https://github.com/olivier-stasse/master-board/issues/9>`_ from open-dynamic-robot-initiative/jviereck_adc
  Add support for reading and printing ADC values from the cards
* Set SP_QN_ADC and UD_QN_ADC from 14 back to 16
* Merge branch 'master' into jviereck_adc
* Merge pull request `#14 <https://github.com/olivier-stasse/master-board/issues/14>`_ from open-dynamic-robot-initiative/jviereck_motor_si_units
  Changes motor position, velocities, kp and kd to SI units
* Merge pull request `#17 <https://github.com/olivier-stasse/master-board/issues/17>`_ from paLeziart/master
  [SDK] Python bindings of MasterBoardInterface, MotorDriver and Motor …
* [SDK] Python bindings of MasterBoardInterface, MotorDriver and Motor classes with Boost + example.py script
* Changes motor position, velocities, kp and kd to SI units
* Add support for reading and printing ADC values from the cards
* Merge pull request `#7 <https://github.com/olivier-stasse/master-board/issues/7>`_ from open-dynamic-robot-initiative/mnaveau/catkin_compatiblity
  catkin compatiblity
* fix the move of the sdk include to a sub-folder
* move the include in a subfolder call master_board_sdk for general packaging consistency
* moved all the files to clean the sdk folder
* Contributors: AlexisPotier, Felix Widmaier, Guilhem Saurel, Julian Viereck, Maxime K, Maximilien Naveau, MaximilienNaveau, Miroslav Bogdanovic, Naveau, Pierre-Alexandre Leziart, Thomas Flayols, jviereck@tuebingen.mpg.de, maximekli, paLeziart, thomasfla
