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
