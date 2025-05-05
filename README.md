# Event Driven Automation (SaltStack Module)

This SaltStack module automates the setup and monitoring of an nginx service.
It installs and configures nginx, sets up a Salt beacon to monitor its status.
It uses Salt reactor to automatically restart nginx if it stops.

## Setup

**1. Navigate and create a new directory called "salt"**

<pre>
$ cd /srv && mkdir salt
</pre>

**2. Clone the repository**

<pre>
$ git clone https://github.com/HMJ3/h5-moduuli.git
</pre>

**3. Move the reactor configuration file**

<pre>
$ sudo mv h5-moduuli/reactor/reactor.conf /etc/salt/master.d/
</pre>

**4. Restart the Salt master to apply changes**

<pre>
$ sudo systemctl restart salt-master.service
</pre>

**5. Run the Salt state on your minions**

<pre>
$ sudo salt '*' state.apply h5-moduuli
</pre>
