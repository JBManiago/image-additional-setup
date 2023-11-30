# image-additional-setup

TODO
Give existing root user a password.

1. add the following in the local.conf 
###########################################
EXTRA_IMAGE_FEATURES ?= "allow-root-login"

INHERIT +=  "extrausers"
PASSWD = "$6$11550452$6eJmUf6GSaMSh88vnfttcU6fDfa6Q82Ki/f7lz49P3ZEcVfcbqEKRS1vH1iCb3IhIhpJoA0FNtHylNFrhf/fK."
EXTRA_USERS_PARAMS = "\
    usermod -p '${PASSWD}' root; \
    "
##########################################

2. Add the following in ./../meta/recipes-connectivity/openssh/openssh/sshd_config

PermitRootLogin yes
PasswordAuthentication yes
