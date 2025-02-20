cmake_minimum_required(VERSION 3.16)

project(modules_planning_math_discretized_points_smoothing)
message("${Green} [info] modules_planning_math_discretized_points_smoothing cmakelist ${ColourReset}")

add_library(modules_planning_math_discretized_points_smoothing_cos_theta_smoother  SHARED
  cos_theta_smoother.cc
)
set_target_properties(modules_planning_math_discretized_points_smoothing_cos_theta_smoother  PROPERTIES LINKER_LANGUAGE CXX)
target_link_libraries(modules_planning_math_discretized_points_smoothing_cos_theta_smoother
  modules::planning::math::discretized_points_smoothing::cos_theta_ipopt_interface
  cyber::common::log
  modules::planning::proto::math::cos_theta_smoother_config_cc_proto
  ${ipopt}
)
add_library(modules::planning::math::discretized_points_smoothing::cos_theta_smoother  ALIAS   modules_planning_math_discretized_points_smoothing_cos_theta_smoother)

add_library(modules_planning_math_discretized_points_smoothing_cos_theta_ipopt_interface  SHARED
  cos_theta_ipopt_interface.cc
)
set_target_properties(modules_planning_math_discretized_points_smoothing_cos_theta_ipopt_interface  PROPERTIES LINKER_LANGUAGE CXX)
target_link_libraries(modules_planning_math_discretized_points_smoothing_cos_theta_ipopt_interface
  cyber::common::log
  ${adolc}
  ${ipopt}
)
add_library(modules::planning::math::discretized_points_smoothing::cos_theta_ipopt_interface  ALIAS   modules_planning_math_discretized_points_smoothing_cos_theta_ipopt_interface)

add_library(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_smoother  SHARED
  fem_pos_deviation_smoother.cc
)
set_target_properties(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_smoother  PROPERTIES LINKER_LANGUAGE CXX)
target_link_libraries(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_smoother
  modules::planning::math::discretized_points_smoothing::fem_pos_deviation_ipopt_interface
  modules::planning::math::discretized_points_smoothing::fem_pos_deviation_osqp_interface
  modules::planning::math::discretized_points_smoothing::fem_pos_deviation_sqp_osqp_interface
  cyber::common::log
  modules::planning::proto::math::fem_pos_deviation_smoother_config_cc_proto
  ${ipopt}
)
add_library(modules::planning::math::discretized_points_smoothing::fem_pos_deviation_smoother  ALIAS   modules_planning_math_discretized_points_smoothing_fem_pos_deviation_smoother)

add_library(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_ipopt_interface  SHARED
  fem_pos_deviation_ipopt_interface.cc
)
set_target_properties(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_ipopt_interface  PROPERTIES LINKER_LANGUAGE CXX)
target_link_libraries(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_ipopt_interface
  cyber::common::log
  ${adolc}
  ${ipopt}
)
add_library(modules::planning::math::discretized_points_smoothing::fem_pos_deviation_ipopt_interface  ALIAS   modules_planning_math_discretized_points_smoothing_fem_pos_deviation_ipopt_interface)

add_library(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_osqp_interface  SHARED
  fem_pos_deviation_osqp_interface.cc
)
set_target_properties(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_osqp_interface  PROPERTIES LINKER_LANGUAGE CXX)
target_link_libraries(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_osqp_interface
  cyber::common::log
  ${osqp}
)
add_library(modules::planning::math::discretized_points_smoothing::fem_pos_deviation_osqp_interface  ALIAS   modules_planning_math_discretized_points_smoothing_fem_pos_deviation_osqp_interface)

add_library(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_sqp_osqp_interface  SHARED
  fem_pos_deviation_sqp_osqp_interface.cc
)
set_target_properties(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_sqp_osqp_interface  PROPERTIES LINKER_LANGUAGE CXX)
target_link_libraries(modules_planning_math_discretized_points_smoothing_fem_pos_deviation_sqp_osqp_interface
  cyber::common::log
  ${osqp}
)
add_library(modules::planning::math::discretized_points_smoothing::fem_pos_deviation_sqp_osqp_interface  ALIAS   modules_planning_math_discretized_points_smoothing_fem_pos_deviation_sqp_osqp_interface)

