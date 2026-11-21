Warp Core Bench
CPU and GPU physics benchmarking inside a sci-fi reactor.

Warp Core Bench combines CPU, CUDA, and Vulkan benchmark paths with a customizable reactor viewer, repeated-run scoring, and local result reports. Run a benchmark, inspect its consistency, and compare results from matching workloads and protocols.

Developer: ShrimpBrime™ · Warp9-Systems™

<iframe width="458" height="814" src="https://www.youtube.com/embed/sXN0Pnyt614" title="WarpCore New Features Short" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


Warp Core Bench

CPU and GPU physics benchmarking inside an interactive sci-fi reactor.

Warp Core Bench combines CPU PhysX, CUDA GPU PhysX, and Vulkan compute benchmarks with repeated-run scoring, local reports, and online leaderboard submissions.

Backend

Workload

Hardware

CPU

NVIDIA PhysX CPU simulation, with Classic and Extended profiles

Supported x64 CPUs, independent of GPU vendor

CUDA

NVIDIA PhysX GPU simulation using the fixed BOX150K workload

Compatible NVIDIA GPU and driver

Vulkan

Compute-based physics simulation using the fixed 8,192-sphere workload

Compatible Vulkan compute GPU and driver

Each backend has its own workload and scoring method. Compare results within the same backend, protocol, and run profile. CPU PhysX, CUDA BOX150K, and Vulkan sphere scores are separate measurements. The Vulkan simulation uses Warp Core’s own compute solver rather than NVIDIA PhysX.

Features

Live leaderboards: Submit eligible ranked results and compare personal bests at leaderboard.warpcorebench.com.

Scoring validation: Ranked submissions use server-issued run tickets, timing-plausibility checks, and server-side score calculations.

Shareable results: Submitted runs receive a public results page. The app includes a Results screenshot when capture succeeds.

Repeated-run scoring: Review individual passes, aggregate results, and repeatability information.

Measurement isolation: Benchmarks run in worker processes while the reactor viewer pauses its simulation and holds its 3D presentation.

Interactive Reactor Demo: Explore particle palettes, pulse direction, turbulence, glow, bloom, alerts, and Warp 9 effects.

Repair mode: Operate a mouse-controlled welding arm alongside automated repair arms and particle sparks.

Physics firing range: Launch particles and use the physics cannon to interact with stacks of simulated boxes.

Console controls: Collapsible armrest panels provide access to reactor actions and presentation settings.

Demo telemetry: View live simulation information while interacting with the reactor.

Appearance controls: Choose an installed TrueType font and automatic or manual interface scaling.

Local reports and screenshots: Save results for comparison and capture the application directly.

Experimentation tools: Explore additional physics workloads separately from the ranked benchmark protocols.

Signed portable distribution: One executable contains the application, workers, assets, notices, and required runtime files.

Download and run

Download the latest portable release from this repository’s Releases section.

Extract the ZIP and launch WarpCoreBench.exe.

Open Benchmarks and select CPU, CUDA, or Vulkan.

Start a run and review the score, individual passes, and consistency information.

No installer or administrator privileges are required. Users do not need Visual Studio, CMake, the PhysX SDK, CUDA Toolkit, or Vulkan SDK.

Ranked submissions

Enable Ranked before starting a desktop benchmark.

Enter your player name and review the Privacy information.

Complete the benchmark.

Select Submit to send an eligible result.

Use Copy Link to share the public results page, or View Leaderboard to open the selected board.

The leaderboard displays personal bests. Keep ranked_player_live.txt private and retain it to preserve access to your player identity.

Ranked submissions include benchmark measurements, hardware information, and a Results screenshot when capture succeeds. Review the privacy notice before submitting.

Requirements

Windows 10 or Windows 11, 64-bit.

A graphics driver capable of running the reactor viewer.

A supported NVIDIA GPU and compatible driver for CUDA benchmarks.

A compatible Vulkan compute GPU and driver for Vulkan benchmarks.

Internet access for ranked runs, submissions, and online leaderboards.

Optional Vulkan validation-layer checks require the validation layer to be installed separately. Ordinary Vulkan benchmark runs do not require it.

Scoring and consistency

CPU benchmarks offer Classic and Extended protocols with 5-, 10-, or 25-pass options.

CUDA BOX150K uses 150,000 boxes, five measured passes, and 240 measured simulation steps per pass. The interface displays CUDA points alongside the underlying scene-steps-per-second measurement.

Vulkan 8K runs three fresh worker processes consecutively, measures each for approximately ten seconds, and uses the median scene steps per second as its score. Its repeatability limit is 5%, calculated as:

Spread (%) = 100 × (maximum run rate − minimum run rate) / median run rate

Incomplete, invalid, mismatched, or excessive-spread Vulkan sessions withhold the score while retaining reports.

For useful comparisons, use matching protocols and run settings, and record application versions, drivers, and tuning changes. Scores describe performance in specific physics workloads rather than overall gaming performance or system stability.

Local data and portable operation

Results and preferences are stored under:

%LOCALAPPDATA%\WarpCoreBench

Ranked mode is off by default. Local benchmark reports are not automatically submitted. Ranked mode contacts the leaderboard service to obtain a run ticket; completed results are uploaded when Submit is selected. Command-line runs remain local.

The portable executable extracts its components into a fresh per-user runtime folder, verifies their SHA-256 hashes, and holds the extracted files against modification while the application runs. Normal exit removes the extracted launch files; saved results remain available. Forced termination can leave a runtime folder behind.

For taskbar pinning, create or pin a shortcut to the outer WarpCoreBench.exe, rather than the running application inside its temporary extraction folder.

Updates and file verification

Open About → Check for Updates to check for a newer release. Close Warp Core Bench before replacing the portable executable.

Verify the executable’s Digital Signatures tab and the supplied SHA-256 information. Code signing identifies the publisher and protects file integrity.

Building from source

Development requires Visual Studio 2022 C++ build tools, CMake, and a matching compiled GPU-enabled PhysX SDK. Full portable packaging also requires the Vulkan worker.

Run BUILD_AND_SIGN.cmd using the configured signing environment.

The v1.0.8 packaging workflow produces:

artifacts\publish\WarpCoreBench.exe

artifacts\WarpCoreBench_v1.0.8_PORTABLE.zip

Documentation and third-party components

The application’s About section provides access to instructions, photosensitivity information, the EULA, and third-party notices.

Built with NVIDIA PhysX, raylib, and Vulkan headers. Applicable licenses and notices accompany the application. Product and technology names belong to their respective owners.

Developer: ShrimpBrime™ · Warp9-Systems™



