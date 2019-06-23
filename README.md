# octavia-cert-generate
Create generic CAs and certificates for use with Openstack Octavia

This is an Ansible playbook and role to create a generic set of CAs and certificates 
for use with Openstack Octavia. It is meant to fill a gap in kolla-ansible, but can 
serve any Octavia deployment. It will give you what you need without any modifications,
but see "Usage" below for customization.

All credit for the code goes to the Openstack Ansible team. I just stripped out the 
certificate generation bits for yours and my enjoyment. This was thrown together in 
20 minutes, so obviously no warranties. It won't break anything though, and hopefully
it will get you where you need to go.


Usage:

After cloning this repo, update roles/octavia-certs/defaults/main.yml to suit your 
needs. You can provide your own domains, validity time, and all those other certifiate
goodies.

You will also want to edit the playbook itself (main.yml in the root directory) to 
create a decent CA password. You will need to feed this to Octavia.

Finally, just run the playbook:

ansible-playbook -i ansible-hosts main.yml


