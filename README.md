Imagine is a small tool that creates a Vagrant base image. I maintain for my personal use and learning.
Other tools like [VeeWee](https://github.com/jedi4ever/veewee) or [BoxGrinder](http://boxgrinder.org/)
would do the job very well but I wanted to get my hands dirty and solve the same problem using good old Bash.

To achieve our goal, we need the official Centos 6 ISO image, a Bash script and a kickstart script.

This is a work in progress:
* the script is geared toward OSX and you will need to adapt it for other operating systems,
* some of the hardcoded code would need to adapted to your requirement.

Please find the inital blog post here on [here].

## Command Line

If you look under imagine/virtualbox, you will find the create-base-image command which is used like this:

<blockquote>
    create-base-image vmname iso_file kickstart_file
</blockquote>

where
* *vmname* is the name of the base image,
* *iso_file* is the path to the download Centos 6 ISO on your file system,
* *kickstart_file* is the kickstart file that will be used to customize your base image.

You will need to download Centos 6 base image from a
[mirror](http://isoredirect.centos.org/centos/6/isos/x86_64/) near you.

If you have download the CentOS-6.3-x86_64-bin-DVD1.iso base image in the /tmp directory,
the following command will automatically create a new base image with the vagrant user
in the ~/stores/ovf/test directory.

<blockquote>
./create-base-image test /tmp/CentOS-6.3-x86_64-bin-DVD1.iso centos6-ks.cfg
</blockquote>

You can change the target directory either by modifying the Bash script or by setting the OVF_STORE to the root
your ovf store.