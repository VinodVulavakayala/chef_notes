# chef_notes
https://www.inspec.io/docs/
https://dev-sec.io/
https://www.inspec.io/docs/reference/profiles/
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

When the lock file is created it will cache the all dependencies and generate .lock file

https://learn.chef.io/tracks/integrated-compliance#/

https://learn.chef.io/tracks/local-development-and-testing#/
https://learn.chef.io/modules/create-a-custom-profile#/
https://learn.chef.io/modules/explore-inspec-resources#/


control (line 12) is followed by the control's name. Each control in a profile has a unique name.
impact (line 13) measures the relative importance of the test and must be a value between 0.0 and 1.0.
title (line 14) defines the control's purpose.
desc (line 15) provides a more complete description of what the control checks for.
describe (lines 16 — 18) defines the test. Here, the test checks for the existence of the /tmp directory.


In Ruby, the do and end keywords define a block. An InSpec control always contains at least one describe block. However, a control can contain many describe blocks.

Understand a describe block's structure
As with many test frameworks, InSpec code resembles natural language. Here's the format of a describe block.

describe <entity> do
  it { <expectation> }
end
Entity:  example, a package name, service, file, or network port.
  
The <expectation> part specifies the desired result or expected state.
 example, that a port should be open

https://www.inspec.io/docs/reference/matchers/


Complience test are  written in Inspec
What cookbook can be used to send compliance data to compliance server during a chef-client run?:
Audit cookbook

Where are compliance profiles stored?:
On Chef Automate Compliance server.
/var/chef/cache/cookbooks/audit/recipes/default.rb

