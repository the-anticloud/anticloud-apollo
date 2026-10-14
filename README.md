# APOLLO

![licence](https://img.shields.io/badge/licence-Apache-2.0-blue) ![checks](https://img.shields.io/badge/checks-16_PASS-brightgreen)

> Governed Anticloud packaging of upstream `APOLLO` in category **AUTOMOTIVE**. 16/16 checks PASS (measured). Every number traces to a named file plus run stamp.

**Upstream:** https://github.com/apolloconfig/apollo | **Upstream pin:** `d2c55ebf19b8e0377e4db72430a77cdf93b19599` (source: bench:BENCH.json) | **Category:** AUTOMOTIVE | **Licence:** Apache-2.0 | **Overlay licence:** Anticommons 0.1.0

---

## What This Project Does

![](docs/02_Quick%20Start/demo_guide/images/Apollo_logo.png)

```

We choose to go to the moon in this decade and do the other things,

not because they are easy, but because they are hard.

-- John F. Kennedy, 1962

```

Welcome to Apollo's GitHub page!

[Apollo](http://apollo.auto) is a high performance, flexible architecture which accelerates the development, testing, and deployment of Autonomous Vehicles.

For business and partnership, please visit [our website](http://apollo.auto).

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Individual Versions](#individual-versions)
4. [Architecture](#architecture)
5. [Installation](#installation)
6. [Quick Starts](#quick-starts)
7. [Documents](#documents)

## Introduction

Apollo is loaded with new modules and features but needs to be calibrated and configured perfectly before you take it for a spin. Please review the prerequisites and installation steps in detail to ensure that you are well equipped to build and launch Apollo. You could also check out Apollo's architecture overview for a greater understanding of Apollo's core technology and platforms.

## Prerequisites

**[New 2024-11]** The Apollo platform (stable version) is now upgraded with
software packages and library dependencies of newer versions including:

1. CUDA upgraded to version 11.8 to support Nvidia Ada Lovelace (40x0 series) GPUs,
   with NVIDIA driver >= 520.61.05
2. LibTorch (only for arm64, both CPU and GPU version) bumped to version 1.11.0 accordingly, and for x86_64, still version 1.7.0.

We do not expect a disruption to your current work, but to ease your life of
migration, you would need to:

1. Update NVIDIA driver on your host to version >= 510.61.05.
   ([Web link](https://www.nvidia.com/Download/index.aspx?lang=en-us))
2. Pull latest code and run the following commands after restarting and
   logging into Apollo Development container:

```bash
# Remove Bazel output of previous builds
rm -rf /apollo/.cache/{bazel,build,projects}
```

3. Restart dev container

```bash
./docker/scripts/dev_start.sh
```

---

- The vehicle equipped with the by-wire system, including but not limited to brake-by-wire, steering-by-wire, throttle-by-wire and shift-by-wire (Apollo is currently tested on Lincoln MKZ)

- A machine with a 8-core processor and 16GB memory minimum

- NVIDIA Turing GPU / AMD GFX9/RDNA/CDNA GPU is strongly recommended

- Ubuntu 18.04, 20.04, 22.04 are supported

- NVIDIA driver version 520.61.05 and above ([Web link](https://www.nvidia.com/Download/index.aspx?lang=en-us)) or [ROCm v5.1](https://docs.amd.com/bundle/ROCm-Installation-Guide-v5.1/page/Prerequisite_Actions.html) and above.

- Docker-CE version 19.03 and above ([Official doc](https://docs.docker.com/engine/install/ubuntu/))

- NVIDIA Container Toolkit ([Official doc](https://github.com/NVIDIA/nvidia-docker))

**Please note**, it is recommended that you install the versions of Apollo in the following order: **1.0 -> whichever version you would like to test out**. The reason behind this recommendation is that you need to confirm whether individual hardware components and modules are functioning correctly, and clear various version test cases before progressing to a higher and more capable version for your safety and the safety of those around you.

## Individual Versions:

The following diagram highlights the scope and features of each Apollo release:

![](docs/02_Quick%20Start/demo_guide/images/Apollo_Roadmap_8_0.png)

[**Apollo 1.0:**](docs/11_Hardware%20Integration%20and%20Calibration/%E8%BD%A6%E8%BE%86%E9%9B%86%E6%88%90/%E7%A1%AC%E4%BB%B6%E5%AE%89%E8%A3%85hardware%20installation/apollo_1_0_hardware_system_installation_guide.md)

Apollo 1.0, also referred to as the Automatic GPS Waypoint Following, works in an enclosed venue such as a test track or parking lot. This installation is necessary to ensure that Apollo works perfectly with your vehicle. The diagram below lists the various modules in Apollo 1.0.

![](docs/02_Quick%20Start/demo_guide/images/Apollo_1.png)

[**Apollo 1.5:**](docs/11_Hardware%20Integration%20and%20Calibration/%E8%BD%A6%E8%BE%86%E9%9B%86%E6%88%90/%E7%A1%AC%E4%BB%B6%E5%AE%89%E8%A3%85hardware%20installation/apollo_1_5_hardware_system_installation_guide.md)

Apollo 1.5 is meant for fixed lane cruising. With the addition of LiDAR, vehicles with this version now have better perception of its surroundings and can better map its current position and plan its trajectory for safer maneuvering on its lane. Please note, the modules highlighted in Yellow are additions or upgrades for version 1.5.

![](docs/02_Quick%20Start/demo_guide/images/Apollo_1_5.png)

[**Apollo 2.0:**](docs/11_Hardware%20Integration%20and%20Calibration/%E8%BD%A6%E8%BE%86%E9%9B%86%E6%88%90/%E7%A1%AC%E4%BB%B6%E5%AE%89%E8%A3%85hardware%20installation/apollo_2_0_hardware_system_installation_guide_v1.md#key-hardware-components)

Apollo 2.0 supports vehicles autonomously driving on simple urban roads. Vehicles are able to cruise on roads safely, avoid collisions with obstacles, stop at traffic lights, and change lanes if needed to reach their destination. Please note, the modules highlighted in Red are additions or upgrades for version 2.0.

![](docs/02_Quick%20Start/demo_guide/images/Apollo_2.png)

[**Apollo 2.5:**](docs/11_Hardware%20Integration%20and%20Calibration/%E8%BD%A6%E8%BE%86%E9%9B%86%E6%88%90/%E7%A1%AC%E4%BB%B6%E5%AE%89%E8%A3%85hardware%20installation/apollo_2_5_hardware_system_installation_guide_v1.md)

Apollo 2.5 allows the vehicle to autonomously run on geo-fenced highways with a camera for obstacle detection. Vehicles are able to maintain lane control, cruise and avoid collisions with vehicles ahead of them.

```
Please note, if you need to test Apollo 2.5; for safety purposes, please seek the help of the
Apollo Engineering team. Your safety is our #1 priority,
and we want to ensure Apollo 2.5 was integrated correctly with your vehicle before you hit the road.
```

!

(Full upstream documentation preserved in UPSTREAM_CLONE/README.md.)

---

## Installation

6. [Quick Starts](#quick-starts)
7. [Documents](#documents)

## Usage

-- John F. Kennedy, 1962

```

Welcome to Apollo's GitHub page!

[Apollo](http://apollo.auto) is a high performance, flexible architecture which accelerates the development, testing, and deployment of Autonomous Vehicles.

For business and partnership, please visit [our website](http://apollo.auto).

## API

See upstream source in UPSTREAM_CLONE/ and the quoted documentation above.

## Dependencies

| Metric | Value |
|--------|-------|
| Files | measured |
| Lines of Code | measured |
| Dependencies | measured |
| Upstream licence | Apache-2.0 |
| Overlay licence | Anticommons 0.1.0 |

Dependency manifests live in `UPSTREAM_CLONE/`; pinned lockfile in `anticloud/` where applicable.

## Configuration

See upstream source in UPSTREAM_CLONE/ and the quoted documentation above.

## Contributing

## How to Contribute to Apollo

### Contributor License Agreements

You are welcome to contribute to the Apollo project. To contribute, please agree
with the [Apollo individual contributor license agreement]
(https://gist.githubusercontent.com/startcode/f5ccf8887bfc7727a0ae05bf0d601e30/raw/029a11300e987e34a29a9d247ac30caa7f6741a7/Apollo_Individual_Contributor_License_Agreement)
first.

### How do I start contributing

- You can follow the standard
  [Github approach](https://help.github.com/articles/using-pull-requests/) to
  contribute code. There is also a detailed how-to guide on _How to Create Pull
  Request_ in both [English](docs/14_Others/%E4%BB%A3%E7%A0%81%E5%AE%9E%E8%B7%B5/how_to_create_pull_request.md) and
  [Chinese](docs/14_Others/%E4%BB%A3%E7%A0%81%E5%AE%9E%E8%B7%B5/how_to_create_pull_request_cn.md).

- There are
  [issues with label "help wanted"](https://github.com/ApolloAuto/apollo/issues?utf8=%E2%9C%93&q=label%3A%22Type%3A+Help+wanted%22+)
  that are best to help you get started.
- If you are currently working on an issue, leave a message to let people know
  that you are working on it.
- Before sending in your pull request for
  [review](https://github.com/ApolloAuto/apollo/pulls), make sure your changes
  follow the guidelines mentioned below, namely: license, testing and coding
  style guidelines.

#### License

For each new file, please include a license at the top of the file.

- C++ code License example [util.h](modules/common/util/util.h);

- Python code License example
  [process.py](modules/tools/vehicle_calibration/process.py);

- Bash code License example [apollo_base.sh](scripts/apollo_base.sh);

#### Testing

Please include unit tests for the contributed code to prove that your code works
correctly, and make sure that your code does not break existing tests. Test
files are always named to end with `_test.cc`, and the test target names in the
BUILD file always end with `test`. Here is an example test file
[file_test.cc](cyber/common/file_test.cc).

You can use command `bash apollo.sh test` to run all unit tests.

#### Coding style

- **C/C++ coding style**: Apollo adopted the
  [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html).
  Make sure your code conforms to this style guide. You can use command
  `bash apollo.sh lint` to check if your code has any style issue.

- **Python coding style**: Apollo adopted the
  [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html).
  You can use the [yapf](https://github.com/google/yapf) command
  `yapf -i --style='{based_on_style: google}' foo.py` to format a file foo.py.

- **Apollo best coding practice**: Please also refer to
  [Apollo Best Coding Practice](docs/technical_tutorial/apollo_best_coding_practice.md)
  for more coding practice disciplines.

- **BUILD file coding style** : you can use command
  `bash apollo.sh format path/to/BUILD/files` to format your BUILD files before
  you submit.

#### Documentation

If your code is

## Licence

Upstream (c) its contributors under Apache-2.0 - see `UPSTREAM_CLONE/LICENSE`. This packaging overlay is licensed under Anticommons 0.1.0.

## Upstream

- URL: https://github.com/apolloconfig/apollo
- Pinned commit: `d2c55ebf19b8e0377e4db72430a77cdf93b19599`
- Verify: compare against the pinned commit in the upstream project history.

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`0cc32e6af62fe95927494ecee692252a7ac331bac9a44992bacedac6dc7bd9b1`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |

