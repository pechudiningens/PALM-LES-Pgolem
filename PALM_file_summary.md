# PALM `.f90` File Summary

This summary groups the `.f90` source files in `/user/kudo8453/palm/current_version/MAKE_DEPOSITORY_storm` by their stated purpose, using the `! Description:` header blocks from each file.

---

## 1. Advection schemes
Compute advection terms for scalars and momentum components.

| File | Header description |
|---|---|
| `advec_s_bc.f90` | Scalar advection with Bott-Chlond scheme |
| `advec_s_pw.f90` | Scalar advection with Piacsek-Williams scheme |
| `advec_s_up.f90` | Scalar advection with upstream scheme |
| `advec_u_pw.f90` | u-component advection with Piacsek-Williams |
| `advec_u_up.f90` | u-component advection with upstream |
| `advec_v_pw.f90` | v-component advection with Piacsek-Williams |
| `advec_v_up.f90` | v-component advection with upstream |
| `advec_w_pw.f90` | w-component advection with Piacsek-Williams |
| `advec_w_up.f90` | w-component advection with upstream |
| `advec_ws.f90` | Scalar/momentum advection with Wicker-Skamarock 5th-order flux formulation |

---

## 2. Core dynamics and prognostic equations
Main solver terms: prognostic equations, buoyancy, Coriolis, pressure correction, large-scale forcing.

| File | Header description |
|---|---|
| `prognostic_equations.f90` | Solving the prognostic equations |
| `dynamics_mod.f90` | Contains the dynamics of PALM |
| `buoyancy.f90` | Buoyancy term in the equation of motion |
| `coriolis.f90` | Computation of all Coriolis terms |
| `pres.f90` | Divergence, Poisson solve for perturbation pressure, velocity correction |
| `subsidence_mod.f90` | Large-scale subsidence/ascent tendency |
| `damping_mod.f90` | Damping module (inertial oscillation damping) |

---

## 3. Diffusion terms
Subgrid-scale diffusion for scalars and velocity components.

| File | Header description |
|---|---|
| `diffusion_s.f90` | Diffusion term of scalar quantities |
| `diffusion_u.f90` | Diffusion term of u-component |
| `diffusion_v.f90` | Diffusion term of v-component |
| `diffusion_w.f90` | Diffusion term of w-component |

---

## 4. Turbulence closure
Subgrid-scale models and 1D precursor.

| File | Header description |
|---|---|
| `turbulence_closure_mod.f90` | Available turbulence closures |
| `model_1d_mod.f90` | 1D model to initialize 3D arrays |

---

## 5. Surface, subsurface, canopy, and urban models
Surface energy balance, soil, urban canopy, ocean, plant canopy.

| File | Header description |
|---|---|
| `surface_mod.f90` | Surface data structures for surface-adjacent grid cells |
| `surface_layer_fluxes_mod.f90` | Diagnostic surface-layer fluxes via Newton iteration |
| `surface_data_handling.f90` | Surface array allocation, restart I/O, boundary conditions |
| `surface_data_output_mod.f90` | Surface data output |
| `land_surface_model_mod.f90` | Land surface model with multi-layer soil scheme |
| `urban_surface_mod.f90` | Urban Surface Model (USM) |
| `slurb_mod.f90` | Single-layer urban surface model (SLUrb) |
| `ocean_mod.f90` | Ocean mode: salinity, equation of state, Stokes force, wave breaking |
| `plant_canopy_model_mod.f90` | Canopy model: LAD profile, momentum/heat/scalar sinks and sources |
| `dcep_mod.f90` | DCEP multi-layer urban canopy parametrization |
| `indoor_model_mod.f90` | Indoor climate model |

---

## 6. Radiation
Shortwave/longwave transfer and UV.

| File | Header description |
|---|---|
| `radiation_model_mod.f90` | Radiation models/interfaces: constant, simple, RRTMG, RTM |
| `uv_radiation_model_mod.f90` | Erythemally-weighted UV-irradiance |

---

## 7. Cloud microphysics

| File | Header description |
|---|---|
| `bulk_cloud_model_mod.f90` | Calculate bulk cloud microphysics |

---

## 8. Chemistry and aerosols
Gas-phase chemistry, photolysis, wet deposition, aerosol thermodynamics, sectional aerosols.

| File | Header description |
|---|---|
| `chemistry_model_mod.f90` | Main chemistry model |
| `chem_modules.f90` | Chemistry module definitions |
| `chem_gasphase_mod.f90` | Gas-phase chemistry (KPP-generated) |
| `chem_photolysis_mod.f90` | Photolysis models and interfaces |
| `chem_wet_deposition_mod.f90` | EMEP wet deposition |
| `chem_isorropia_mod.f90` | Secondary inorganic aerosols with ISORROPIA |
| `chem_isorropia_interface_mod.f90` | Interface to ISORROPIA library |
| `salsa_mod.f90` | Sectional aerosol module SALSA |
| `dust_emission_and_transport_mod.f90` | Dust emission and transport over sandy surfaces |

---

## 9. Chemistry emissions
Emission schemes for chemistry tracers.

| File | Header description |
|---|---|
| `chem_emissions_mod.f90` | Read chemistry emissions data |
| `chem_emis_biogenic_mod.f90` | Biogenic emissions from vegetation |
| `chem_emis_biogenic_data_mod.f90` | Biogenic emission data (VOCs, trees, PFTs) |
| `chem_emis_domestic_mod.f90` | Domestic emissions |
| `chem_emis_generic_mod.f90` | Generic/user-defined emission mode |
| `chem_emis_nonstationary_mod.f90` | Nonstationary volume-source emissions |
| `chem_emis_pollen_mod.f90` | Pollen emission based on EMPOL model |
| `chem_emis_pollen_data_mod.f90` | Pollen species attributes |
| `chem_emis_pt_source_mod.f90` | Point-source emissions (E-PRTR/GRETA) |
| `chem_emis_traffic_mod.f90` | Traffic emissions |
| `chem_emis_vsrc_mod.f90` | Emission volume-source data structures and API |

---

## 10. Topography and buildings

| File | Header description |
|---|---|
| `topography_mod.f90` | Setup of PALM's topography representation |
| `cut_cell_topography_mod.f90` | Set-up and representation of cut-cell topography |

---

## 11. Boundary conditions, forcing, and inflow/outflow

| File | Header description |
|---|---|
| `boundary_settings_mod.f90` | General settings of specific boundary conditions |
| `large_scale_forcing_nudging_mod.f90` | Large-scale forcings and nudging |
| `nesting_offl_mod.f90` | Offline nesting in larger-scale models |
| `turbulent_inflow_mod.f90` | Turbulent inflow (recycling / read-from-file) |
| `outflow_turbulence.f90` | Copy source-plane values to outflow boundary |
| `synthetic_turbulence_generator_mod.f90` | Generate turbulence at inflow boundary |
| `flow_control_mod.f90` | Flow control (geostrophic wind controller) |

---

## 12. Parallel communication, coupling, and domain nesting

| File | Header description |
|---|---|
| `exchange_horiz_mod.f90` | Ghost-point exchange and cyclic lateral BCs |
| `transpose_mod.f90` | Data resorting for x-to-y transposition |
| `shared_memory_io_mod.f90` | MPI/NetCDF shared-memory array handling |
| `posix_interface_mod.f90` | POSIX system calls for restart file I/O |
| `surface_coupler_mod.f90` | Atmosphere-ocean coupling utilities |
| `pmc_general_mod.f90` | Palm Model Coupler structures/utilities |
| `pmc_parent_mod.f90` | Parent part of Palm Model Coupler |
| `pmc_child_mod.f90` | Child part of Palm Model Coupler |
| `pmc_interface_mod.f90` | Domain nesting interface routines |
| `pmc_handle_communicator_mod.f90` | MPI communicator handling in PMC |
| `pmc_mpi_wrapper_mod.f90` | MPI wrapper for PMC |
| `pmc_particle_interface.f90` | Particle transfer in nested models |

---

## 13. Data output
Write 2D/3D/masked/profile/spectral/time-series/particle/surface data.

| File | Header description |
|---|---|
| `data_output_2d.f90` | Cross-section output |
| `data_output_3d.f90` | 3D-array output |
| `data_output_profiles.f90` | 1D-profile output |
| `data_output_spectra.f90` | Spectra output |
| `data_output_tseries.f90` | Time-series output |
| `data_output_mask.f90` | Masked data output |
| `data_output_flight.f90` | Flight measurement output |
| `data_output_particle_mod.f90` | Particle time-series output |
| `data_output_topo_and_surface_setup_mod.f90` | Topography/surface classification output |
| `data_output_module.f90` | General data-output handling |
| `data_output_netcdf4_module.f90` | NetCDF output |
| `data_output_binary_module.f90` | Binary output |
| `surface_data_output_mod.f90` | Surface data output |
| `print_1d.f90` | List output of 1D profiles |
| `combine_plot_fields.f90` | Post-process/combine plot fields |

---

## 14. NetCDF input

| File | Header description |
|---|---|
| `netcdf_interface_mod.f90` | Define NetCDF dimensions/axes/variables |
| `netcdf_data_input_mod.f90` | Read PALM-standard dynamic/static input |

---

## 15. Restart I/O

| File | Header description |
|---|---|
| `read_restart_data_mod.f90` | Read restart data from binary files |
| `write_restart_data_mod.f90` | Write restart data to binary files |
| `restart_data_mpi_io_mod.f90` | Restart data handling with MPI-IO |
| `check_for_restart.f90` | Set stop flag when restart is needed |
| `wrd_write_string.f90` | Write string values to binary restart files |

---

## 16. Time integration, run control, and statistics

| File | Header description |
|---|---|
| `palm.f90` | Main LES model program |
| `time_integration.f90` | Time integration, statistics, graphic output |
| `time_integration_spinup.f90` | Time integration of non-atmospheric components |
| `timestep.f90` | Compute time step |
| `timestep_scheme_steering.f90` | Set steering factors for prognostic equations |
| `run_control.f90` | Run-control quantities |
| `flow_statistics.f90` | Average profiles and flow quantities |
| `average_3d_data.f90` | Time-averaging of 3D arrays |
| `sum_up_3d_data.f90` | Sum-up 3D arrays for averaging |
| `calc_mean_profile.f90` | Horizontally averaged vertical temperature profile |
| `progress_bar_mod.f90` | Progress bar/file output |

---

## 17. Model initialization

| File | Header description |
|---|---|
| `init_3d_model.f90` | Allocate arrays and initialize 3D model |
| `init_grid.f90` | Create grid-dependent constants |
| `init_advec.f90` | Initialize advection-scheme coefficients |
| `init_masks.f90` | Initialize masked data output |
| `init_pegrid.f90` | Virtual processor topology and local domain bounds |
| `init_vertical_profiles.f90` | Initialize vertical scalar profiles |
| `init_pt_anomaly.f90` | Impose temperature perturbation for advection test |
| `init_rankine.f90` | Initialize Rankine eddy for testing |
| `init_slope.f90` | Initialize sloping-surface fields |
| `parin.f90` | Read run-control namelists |
| `check_parameters.f90` | Check control parameters and derive quantities |
| `header.f90` | Write run header |

---

## 18. FFT and Poisson solvers

| File | Header description |
|---|---|
| `fft_xy_mod.f90` | FFT along x and y |
| `temperton_fft_mod.f90` | FFT by Clive Temperton |
| `singleton_mod.f90` | Multivariate FFT (Singleton's mixed-radix) |
| `cuda_fft_interfaces.f90` | CUDA FFT Fortran interfaces |
| `poisfft_mod.f90` | Poisson solver with 2D spectral method |
| `poisfft_sm_mod.f90` | Shared-memory Poisson-FFT solver |
| `sm_poisfft_mod.f90` | Setup/activation of shared-memory Poisson-FFT |
| `poismg_mod.f90` | Multigrid Poisson solver |
| `poismg_noopt_mod.f90` | Non-optimized multigrid Poisson solver |
| `sor.f90` | SOR Red/Black Poisson solver |
| `tridia_solver_mod.f90` | Thomas algorithm tridiagonal solver |
| `spectra_mod.f90` | Calculate horizontal spectra |

---

## 19. Lagrangian particle model

| File | Header description |
|---|---|
| `lagrangian_particle_model_mod.f90` | Embedded LPM for transport/dispersion |
| `mod_particle_attributes.f90` | Variables for particle transport |
| `user_lpm_advec.f90` | User modification of initial particles |
| `user_lpm_init.f90` | User modification of initial particles |

---

## 20. User-defined extensions

| File | Header description |
|---|---|
| `user_module.f90` | User-defined variables |
| `user_init_3d_model.f90` | Complete user initialization of 3D model |
| `user_init_grid.f90` | User grid initialization |
| `user_init_land_surface.f90` | User land-surface initialization |
| `user_init_urban_surface.f90` | User urban-surface initialization |
| `user_init_radiation.f90` | User radiation initialization |
| `user_init_plant_canopy.f90` | User canopy LAD/drag initialization |
| `user_init_flight_mod.f90` | User flight-measurement initialization |
| `user_flight.f90` | User-defined flight output quantity |
| `user_data_output_mask.f90` | User-defined masked output quantity |
| `user_spectra.f90` | User-defined spectra |

---

## 21. Utilities and infrastructure

| File | Header description |
|---|---|
| `modules.f90` | Global variables |
| `mod_kinds.f90` | Standard kind definitions |
| `array_utilities.f90` | Array utilities |
| `general_utilities.f90` | General utilities |
| `basic_constants_and_equations_mod.f90` | Physical constants and diagnostic functions |
| `global_min_max.f90` | Array min/max and indices |
| `cpulog_mod.f90` | CPU-time measurements |
| `message.f90` | Message handling |
| `local_stop.f90` | Stop program execution |
| `local_system.f90` | OS-specific system calls |
| `local_tremain.f90` | Remaining CPU time |
| `local_tremain_ini.f90` | Initialize CPU-time measurements |
| `palm_date_time_mod.f90` | Date/time calculations |
| `time_to_string.f90` | Convert time to `hh:mm:ss` string |
| `random_function_mod.f90` | Uniform random number generator |
| `random_gauss.f90` | Gaussian random number generator |
| `random_generator_parallel_mod.f90` | Parallel random number generator |
| `compute_vpt.f90` | Virtual potential temperature |
| `diagnostic_output_quantities_mod.f90` | Diagnostic quantities (wind speed, temperature, humidity, etc.) |
| `data_log.f90` | Complete logging of data |
| `check_open.f90` | Check/open file units |
| `close_file.f90` | Close files |
| `vdi_internal_controls.f90` | VDI 3783 Part 9 internal assessment |

---

## 22. Virtual measurements and flights

| File | Header description |
|---|---|
| `virtual_flight_mod.f90` | Virtual flight measurements |
| `virtual_measurement_mod.f90` | Interface between observations and model simulations |

---

## 23. Wind energy

| File | Header description |
|---|---|
| `wind_turbine_model_mod.f90` | Wind turbine effects on flow (ADM-R) |
| `fastv8_coupler_mod.f90` | Coupler to FASTv8 wind-turbine simulations |
| `fastv8_updata.f90` | Additional routines for FASTv8 coupler |

---

## 24. Biometeorology / human comfort

| File | Header description |
|---|---|
| `biometeorology_mod.f90` | Human thermal comfort module |

---

## 25. Multi-agent system

| File | Header description |
|---|---|
| `multi_agent_system_mod.f90` | Pedestrian movement in urban environments |

---

## 26. Gust model

| File | Header description |
|---|---|
| `gust_mod.f90` | Gust model (currently a dummy module) |

---

*All descriptions are taken directly from the `! Description:` header blocks at the top of each `.f90` file.*
