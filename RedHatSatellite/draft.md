sudo /usr/local/NesTools/nespresso-gpg-rhel/sign_push.sh --version=7 --rpm=hapee-2.0r1-lb-1.0.0-213.581.rhel-7.x86_64.rpm

sudo rhnpush -vvv --force --nosig --server=http://hqchsat2/APP --username=satadmin1 --password=7k7NgJG_Vq~a(0x_w=o) --channel=nespresso_v6 -d /rhnsat/Nespresso/6/

/usr/local/NesTools/rhsat-tools/rhsat-pkg-update-rolling.pl

sudo /usr/local/NesTools/rhsat-tools/rhsat-pkg-merge-environments.pl --from=rolling --to=dev
