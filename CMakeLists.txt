#----------------------------------------------------
# 2012 - CMake build generator for PPT book source
#----------------------------------------------------

# we're using v2.8+ by default
cmake_minimum_required(VERSION 2.8.0 FATAL_ERROR)

# preferred threading lib is - POSIX
set(CMAKE_THREAD_PREFER_PTHREAD TRUE)
find_package(Threads REQUIRED)

set(RT_LIB rt)

add_definitions(-DDEBUG)

# build alarm
add_executable(alarm alarm.c)
target_link_libraries(alarm ${CMAKE_THREAD_LIBS_INIT})

# build alarm_thread
add_executable(alarm_thread alarm_mutex.c)
target_link_libraries(alarm_thread ${CMAKE_THREAD_LIBS_INIT})

# build lifecycle
add_executable(lifecycle lifecycle.c)
target_link_libraries(lifecycle ${CMAKE_THREAD_LIBS_INIT})

# build alarm_mutex
add_executable(alarm_mutex alarm_mutex.c)
target_link_libraries(alarm_mutex ${CMAKE_THREAD_LIBS_INIT})

# build trylock
add_executable(trylock trylock.c)
target_link_libraries(trylock ${CMAKE_THREAD_LIBS_INIT})

# build backoff
add_executable(backoff backoff.c)
target_link_libraries(backoff ${CMAKE_THREAD_LIBS_INIT})

# build cond
add_executable(cond cond.c)
target_link_libraries(cond ${CMAKE_THREAD_LIBS_INIT})

# build pipe
add_executable(pipe pipe.c)
target_link_libraries(pipe ${CMAKE_THREAD_LIBS_INIT})

# build crew
add_executable(crew crew.c)
target_link_libraries(crew ${CMAKE_THREAD_LIBS_INIT})

# build server
add_executable(server server.c)
target_link_libraries(server ${CMAKE_THREAD_LIBS_INIT})

# build once
add_executable(once once.c)
target_link_libraries(once ${CMAKE_THREAD_LIBS_INIT})

# build thread_attr
add_executable(thread_attr thread_attr.c)
target_link_libraries(thread_attr ${CMAKE_THREAD_LIBS_INIT})

# build cancel
add_executable(cancel cancel.c)
target_link_libraries(cancel ${CMAKE_THREAD_LIBS_INIT})

# build sched_attr
add_executable(sched_attr sched_attr.c)
target_link_libraries(sched_attr ${CMAKE_THREAD_LIBS_INIT})

# build sched_thread
add_executable(sched_thread sched_thread.c)
target_link_libraries(sched_thread ${CMAKE_THREAD_LIBS_INIT})

# build semaphore_signal
add_executable(semaphore_signal semaphore_signal.c)
target_link_libraries(semaphore_signal ${CMAKE_THREAD_LIBS_INIT} ${RT_LIB})

# build semaphore_wait
add_executable(semaphore_wait semaphore_wait.c)
target_link_libraries(semaphore_wait ${CMAKE_THREAD_LIBS_INIT})

# build sigev_thread
add_executable(sigev_thread sigev_thread.c)
target_link_libraries(sigev_thread ${CMAKE_THREAD_LIBS_INIT} ${RT_LIB})

# build susp
add_executable(susp susp.c)
target_link_libraries(susp ${CMAKE_THREAD_LIBS_INIT})

# build rwlock_main
add_executable(rwlock_main rwlock_main.c rwlock.c)
target_link_libraries(rwlock_main ${CMAKE_THREAD_LIBS_INIT})

# build rwlock_try_main
add_executable(rwlock_try_main rwlock_try_main.c rwlock.c)
target_link_libraries(rwlock_try_main ${CMAKE_THREAD_LIBS_INIT})

# build barrier_main
add_executable(barrier_main barrier_main.c barrier.c)
target_link_libraries(barrier_main ${CMAKE_THREAD_LIBS_INIT})

# build workq_main
add_executable(workq_main workq_main.c workq.c)
target_link_libraries(workq_main ${CMAKE_THREAD_LIBS_INIT} ${RT_LIB})

# build tsd_once
add_executable(tsd_once tsd_once.c)
target_link_libraries(tsd_once ${CMAKE_THREAD_LIBS_INIT})

# build tsd_destructor.c
add_executable(tsd_destructor tsd_destructor.c)
target_link_libraries(tsd_destructor ${CMAKE_THREAD_LIBS_INIT})
