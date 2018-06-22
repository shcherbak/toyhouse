# toyhouse

cat > /etc/apt/sources.list.d/puppet.list
```
# Puppet stretch Repository
deb http://apt.puppetlabs.com stretch puppet

# Puppet stretch Source Repository
# The source repos are commented out by default because we
# do not always make sources available for all packages or
# for all platforms. If you want to access the source repos,
# uncomment the following line.
#deb-src http://apt.puppetlabs.com stretch puppet
```
curl -L https://apt.puppetlabs.com/DEB-GPG-KEY-puppet | sudo apt-key add -