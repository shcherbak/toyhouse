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



.                                                                                                                                                                                                                                                  
├── auth.conf                                                                                                                                                                                                                                      
├── environments
│   ├── default.yaml
│   ├── global
│   │   ├── environment.conf
│   │   ├── manifests
│   │   └── modules
│   │       ├── custom
│   │       ├── dist
│   │       ├── Puppetfile
│   │       └── site
│   ├── production
│   │   ├── environment.conf
│   │   ├── manifests
│   │   └── modules
│   │       ├── custom
│   │       ├── dist
│   │       ├── Puppetfile
│   │       └── site
│   ├── staging
│   │   ├── environment.conf
│   │   ├── manifests
│   │   └── modules
│   │       ├── custom
│   │       ├── dist
│   │       ├── Puppetfile
│   │       └── site
│   └── testing
│       ├── environment.conf
│       ├── manifests
│       └── modules
│           ├── custom
│           ├── dist
│           ├── Puppetfile
│           └── site
├── fileserver.conf
├── hiera
│   ├── domains
│   │   └── my-domain.com.yaml
│   ├── environments
│   │   ├── production.yaml
│   │   ├── staging.yaml
│   │   └── testing.yaml
│   └── hosts
├── hiera.yaml
├── puppet.conf
└── secrets
