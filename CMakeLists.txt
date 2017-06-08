project( FaceTracker )
cmake_minimum_required(VERSION 3.2)

find_package( OpenCV REQUIRED )
include_directories(include
                    ${OpenCV_INCLUDE_DIRS})


add_library(FaceTrackerLib 
				src/lib/Tracker.cc
				src/lib/Patch.cc
				src/lib/PDM.cc
				src/lib/PAW.cc
				src/lib/IO.cc
				src/lib/FDet.cc
				src/lib/FCheck.cc
				src/lib/CLM.cc)


add_executable( FaceTracker src/exe/face_tracker.cc )
target_link_libraries( FaceTracker ${OpenCV_LIBS} FaceTrackerLib)
