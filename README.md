# chef_notes
https://learn.chef.io/modules/try-inspec#/
Check chef version
chef -v

check inspec help
inspec -h

create inspec profile
inspec init name inpec_profile_name

check inspec version
inspec version
inspec detect ---> it will detect version of OS.

execute inspec profile
inpsec exec  path of the profile
inspec exec /profiles/httpd
inspec exec profile.tar.gz

execcute inspec profile remotely
inspec exec auditd -t ssh://root:password@target

linting inspec profile :
inspec check profilename
inspec check auditd

Archive inspec profile for sharing purpose:
inspec archive auditd

execute remote inspec profile
inspec exec https://github.com/learn-chef/auditd/releases/download/v0.1.0/auditd-0.1.0.tar.gz -t ssh://root:password@target

check profiles from community
inspec supermarket profile
inpsec supermarket info profile_name

Check inspec from github code
inspec exec https://github.com/dev-sec/linux-baseline 

run specific control:
inspec exec  https://github.com/dev-sec/linux-baseline --controls package-08

You detected issues both by running InSpec locally and by running InSpec remotely on a target system.
You downloaded a basic InSpec profile and used a community profile from Chef Supermarket.
You limited your InSpec runs to certain controls and formatted the output as JSON so you can generate reports.
You packaged your profile to make it easier to distribute.

Resources:
https://www.inspec.io/docs/
https://dev-sec.io/


inspec.yml -->includes the profile description (required)
controls --->is the directory in which all tests are located (required)
libraries---> is the directory in which all Chef InSpec resource extensions are located (optional)
files---> is the directory with additional files that a profile can access (optional)
README.md--->should be used to explain the profile, its scope, and usage
