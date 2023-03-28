# Changelog

All notable changes to this project will be documented in this file.

## unreleased

### Added

- Variable `ubuntu_release` added and bump default ubuntu release.
- Make prometheus optional and omit all related resources and packages installed via the user data script.
- arm64 instances support.

### Changed

- Remove explicit provider region as variable and use inherited provider
- Don't create eip if var.use_eip = false.
- Use empty string for template file variables for interpolation
- remove backend configuration.
- Update provide version.
- Cleanup tags

## [1.3.0] - 2021-03-23

### Added

- Add SSM parameter creation by Terraform
- Add aws ssm get-parameter for Wireguard server private key
- Add EIP creation
- Add route53 creation
- Add route geolocation

### Changed

- Update README
- Update example

## [1.2.0] - 2021-03-12

### Added
- docker-ce
- docker-compose
- prometheus-wireguard-exporter
- friendly_name support

## [1.1.0] - 2021-03-11

### Added
- Update examples
- Update Readme
- Fix tf code
- Refactor tf variables
- Fix iptables rules
- Upgrade Ubuntu 16.04 > 20.04
- Upgrade aws cli v1 > v2
- Install additional packages on the server for debugging & maintenance
- Support for TF v0.13

## [1.0.0] - 2019-10-13
Note that this release contains breaking changes. Hence the major version bump.

### Added
- Support for TF v0.12
- Support for Network Load Balancers
- Variable `instance_type` added.
- Variable `additional_security_group_ids` added to support more flexibility with security groups.
- Variable `eip_id` added to pass in an EIP object
- `asg_min_size`, `asg_max_size`, and `asg_desired_capacity` variables for autoscaling groups.
- Variable `wg_persistent_keepalive` to set keepalive in seconds. Set to 0 to disable.

### Changed
- Variable `public_subnet_ids` renamed to `subnet_ids`
- Ubuntu AMI used will now default to the latest.

### Removed
- An EIP is no longer created in this module, in order to support the option to use a ELB. Instead, a EIP ID must be passed in, if that is the desired configuration.

## [0.0.2] - 2019-03-02
### Added
- Multi-client support via the module variable.
- This CHANGELOG
### Removed
- Single-client public key via AWS SSM as it now conflicts with the module variable method.

## [0.0.1] - 2019-02-24
### Added
- Working module to deploy WireGuard with single client support.
