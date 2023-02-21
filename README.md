# Enclave.net
Enclave.NET is an Open Source project born to help the everyday developer leverage the Confidential Computing capabilities provided by the latest generation of Intel processors. The key issue with the currently available toolking is that both the Intel SGX SDK and Open Enclave SDK can be leveraged (efficiently) only from unamanaged code (C/C++) hence making the learning curve much more steeper for developer who predomintaly have a purely .NET background. With Enclave.NET my goal is to bridge this gap and allow everyone to build Confidential Computing workloads without to much trouble.

## What is Intel SGX and why it matters
Quoting Wikipedia, the only source that I found that was able to privide a clear and markering-jargon free definition for Intel SGX (acronym for Intel Software Guard Extensions) states that:

>Intel Software Guard Extensions (SGX) is a set of security-related instruction codes that are built into some Intel central processing units (CPUs). They allow user-level and operating system code to define protected private regions of memory, called enclaves. SGX is designed to be useful for implementing secure remote computation, secure web browsing, and digital rights management (DRM). Other applications include concealment of proprietary algorithms and of encryption keys. SGX involves encryption by the CPU of a portion of memory (the enclave). Data and code originating in the enclave are decrypted on the fly within the CPU, protecting them from being examined or read by other code, including code running at higher privilege levels such the operating system and any underlying hypervisors.

With the above definition ne can understand how this very deep level of protection could benefit application running on the Cloud or in any other shared and untrusted environment. Unfortunately, the SGX capabilities will not land in consumer CPU due to a pivot by Intel in 2021 making the above capability a prerogatvive of Server+Cloud CPUs.

## Primer of Confidential Computing
The Intel SGX capabilitiy and in general the ability to create either at the application level or VM level is a key enabler for confidential computing. The Confidential Computing Consurtium provides this definition for this modern type of computation:

>Confidential computing is the protection of data in use using hardware-based Trusted Execution Environments (TEE). A Trusted Execution Environment is commonly defined as an environment that provides a level of assurance of data integrity, data confidentiality, and code integrity. A hardware-based TEE uses hardware-backed techniques to provide increased security guarantees for the execution of code and protection of data within that environment

Microsoft is one the key hyperscaler that are enriching its Cloud portoflio with solutions that allow us to run Confidential Computing workloads in Azure. A great session has been delivered at Ignite (you can watch on demand [here](https://ignite.microsoft.com/en-US/sessions/22182092-2662-41fe-a2a3-31131bcce6cc)) and you can have an overview of the current Microsoft Azure offering for Confidential Computing [here](https://techcommunity.microsoft.com/t5/azure-confidential-computing/bg-p/AzureConfidentialComputingBlog).

## Refrence implementation
Calling native code from managed code has never been as easy tasks, luckly for us Intel released a white paper showcasing how to specifically write a C# application using managed code and all the interop/marshalling code that is required. We plan to build on that sample to provide an easy to use NuGet library that can be easily plugged in any .NET project. The link to that guide can be found, together with the code of the samples used, at [this](https://www.intel.com/content/www/us/en/developer/articles/technical/csharp-application-with-intel-software-guard-extensions.html) link.

## Feature roadmap
In order to give us a plan for the first release of Enclave.NET, we are targeting the following APIs to be available. Of course, along with these methods, we will interop with any required data structure/enumeration required.

### Functions
* oe_create_enclave
* oe_terminate_enclave
* oe_get_seal_key_by_policy
* oe_get_seal_key
* oe_result_str

In general, our goal is to be a 1:1 mapping for the Open Enclave SDK which can be fully explored here: https://openenclave.io/apidocs/v0.5/files.html

## Contribute
This is a project that I maintain on my spare time. I believe that it will serve many workloads in the upcoming future, if you want to be part of the team and contribute to moving this project forward you can reach me on [Twitter](https://twitter.com/itsonlyGianca) or [LinkedIn](https://www.linkedin.com/in/giancarlolelli/) or at the following [email](mailto:gcarlo.lelli@gmail.com) address.

## License
This project is distributed under the **Apache License 2.0** if you don't know that it means, please check out [choosealicense.com](https://choosealicense.com/licenses/apache-2.0/)
