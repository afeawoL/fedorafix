# fedorafix



To just update repo metadata it's dnf makecache

Then to upgrade your installed packages it's dnf upgrade If the cache has expired dnf will automatically update repo metadata.

To be sure you upgrade with fresh repo metadata in one command, as said before, you can do dnf upgrade --refresh

I guess there is a man dnf
}


[fedora]
name=Fedora $releasever - $basearch
#baseurl=http://download.example/pub/fedora/linux/releases/$releasever/Everything/$basearch/os/
#baseurl=http://download.example/pub/fedora/linux/releases/$releasever/Everything/$basearch/os/
metalink=https://mirrors.fedoraproject.org/metalink?repo=fedora-$releasever&arch=$basearch
enabled=1
countme=1
metadata_expire=7d
repo_gpgcheck=0
type=rpms
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-$releasever-$basearch
skip_if_unavailable=False

-----------------

[fedora]
name=Fedora $releasever - $basearch
#baseurl=http://download.fedoraproject.org/pub/fedora/linux/releases/$releasever/Everything/$basearch/os/
metalink=https://mirrors.fedoraproject.org/metalink?repo=fedora-$releasever&arch=$basearch
enabled=1
countme=1
metadata_expire=7d
repo_gpgcheck=0
type=rpm
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-$releasever-$basearch
skip_if_unavailable=False

download.fedoraproject.org

'name=<RepoName>fedora
baseurl=https://mirrors.fedoraproject.org/metalink?repo=fedora-35&arch=x86_64
baseurl=https://
gpgcheck=0
gpgkey=https://insert.repogpg.key.url/' | sudo tee /etc/yum.repos.d/<RepoName>.repo
sudo rpm --import https://insert.repogpg.key.url
