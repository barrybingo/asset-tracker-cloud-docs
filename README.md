# _Bifravst_

> Gvðín gerþu bru af iorþu til himins, er heitir Bifravst.

[![CircleCI](https://circleci.com/gh/bifravst/bifravst/tree/saga.svg?style=svg)](https://circleci.com/gh/bifravst/bifravst/tree/saga)
[![Greenkeeper badge](https://badges.greenkeeper.io/bifravst/bifravst.svg)](https://greenkeeper.io/)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier/)
[![ESLint: TypeScript](https://img.shields.io/badge/ESLint-TypeScript-blue.svg)](https://github.com/typescript-eslint/typescript-eslint)  
[![{DevZone Community](https://img.shields.io/badge/%7BDevZone-community-brightgreen.svg)](https://devzone.nordicsemi.com/search?q=bifravst)
[![Spectrum Chat](https://img.shields.io/badge/Spectrum-chat-blue.svg)](https://spectrum.chat/bifravst)

🚧 Development progress is managed in
[this GitHub Project](https://github.com/orgs/bifravst/projects/1).

❓ You can get in touch by
[creating an issue in this repository](https://github.com/bifravst/bifravst/issues/new),  
or via [DevZone](https://devzone.nordicsemi.com/) (please use the tag
[bifravst](https://devzone.nordicsemi.com/search?q=bifravst) to mark your
questions).  
💬 There is also [a chat on Spectrum](https://spectrum.chat/bifravst).

## Vision

_Bifravst_ aims to provide a concrete end-to-end sample for an IoT product in
the asset tracker space, a _Cat Tracker_.

![Bifravst: Cat Tracker IoT example](./docs/logo-with-text.png)

**With _Bifravst_ developers are enabled to set up a real world IoT solution
using their cloud provider and start adapting the sample firmware and software
for their use case within minutes.**

_Bifravst_ aims to provide answers and best practices to these questions:

- _How can I connect Nordic's long-range chips to my cloud provider?_
- _How do devices send data into the cloud?_
- _How can data be sent to the devices?_
- _How can users and other services interact with devices?_
- _How can I update the application firmware of my devices while they are
  deployed in the field?_

_Bifravst_ is licensed under the [MIT license](./LICENSE).

### Comparison to nRF Connect for Cloud

_Bifravst_ does not aim to replace or superseed nRF Connect for Cloud. It has a
distinctly different scope:

|                                    | [nRF Connect for Cloud](https://www.nordicsemi.com/Software-and-Tools/Development-Tools/nRF-Connect-for-Cloud) | _Bifravst_           |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------- |
| **Development model**              | Closed                                                                                                         | Open                 |
| **License**                        | Commercial                                                                                                     | Open Source          |
| **Cloud vendor support**           | AWS Only                                                                                                       | Multiple             |
| **Feature set**                    | Generalized, large                                                                                             | Specialized, small   |
| **Hosting**                        | managed                                                                                                        | self-hosted          |
| **User Interface**                 | Desktop-Browsers, REST API                                                                                     | Mobile-first web-app |
| **Cloud Tenancy**                  | multi                                                                                                          | single               |
| **Integration of Cloud resources** | custom                                                                                                         | native               |

### Core principles

_Bifravst_ is built around the following principles:

- _teach through showing_: all samples are designed to solve a concrete use-case
  (a _Cat Tracker_) instead of providing generic or abstract solutions.
  _Bifravst_ is not a framework, but a real application.
- _err on the side of security_: _Bifravst_ follows the most robust security
  recommendations of the respective cloud provider.
- _single tenancy_: _Bifravst_ implements a scenario in which all authenticated
  users can be trusted to access all devices. This is a typical scenario in IIoT
  products and simplifies the onboarding of new devices.
- _serverless_: _Bifravst_ uses a serverless architecture as much as possible to
  have near zero costs for the operation during development but provide
  horizontal scaling resources to be used in a production system if needed.
- _cloud native_: _Bifravst_ samples are designed following the respective cloud
  providers' best practices to reduce development efforts due to abstraction.

### System overview and technical considerations

![System overview](./docs/System%20overview.jpg)

Devices connect to the message broker using TLS over TCP. The messaging protocol
is JSON over MQTT. The TLS certificates are generated offline by the developer
to simplify provision during production.

The cloud and web application will be developed using
[TypeScript](https://www.typescriptlang.org/) (a typed superset of JavaScript).
JavaScript is the most popular language according to a
[2019 Stack Overflow survey](https://insights.stackoverflow.com/survey/2019#technology).
All (or at least most) cloud providers provide SDKs in JavaScript.

It provides tools to configure the developers’ cloud account for use with their
devices and the SPA. After the cloud account has been configured it provides the
necessary resources for asset trackers to connect to the message broker and send
and receive messages and the appropriate APIs for the SPA to interact with these
devices.

The mobile-first single-page application (SPA) will be developed using
[create-react-app](https://github.com/facebook/create-react-app) and provides a
reference implementation of a user-interface to control and interact with the
devices.

The web application offers these features:

- User registration including password recovery
  - Optional: User approval by an admin.
- Listing of asset trackers
- Viewing of asset trackers
  - Current and historical sensor data
    - GPS location
    - Battery voltage
    - Accelerometer
  - Configure asset tracker
    - Update interval
    - Sensor threshold
- Managing of asset trackers
  - Delete tracker
  - Firmware update

### Supported Cloud Providers

Support for cloud providers is planned be implemented in this order:

1. [Amazon Web Services](./docs/aws/GettingStarted.md)
1. Amazon Web Services UDP+CoAP support (using a bridge, e.g.
   [Eclipse Californium](https://github.com/eclipse/californium))
1. Google Cloud
1. Alibaba Cloud

---

**Acknowledgments**  
_Nyan Cat by
[Christopher Torres](https://www.youtube.com/watch?v=QH2-TGUlwu4)._  
_Northern Lighs by [Naian Wang](https://unsplash.com/photos/F9wrh2miJLA)._  
_Pin Icon created by Nun from the Noun Project._  
_Cat Icon created by Focus Lab from the Noun Project._  
_Amazon Web Services, the aws logo are trademarks of Amazon.com, Inc. or its
affiliates in the United States and/or other countries._  
_Google and the Google logo are registered trademarks of Google LLC._  
_Microsoft and Azure are registered trademarks of Microsoft Corporation in the
United States and/or other countries._
