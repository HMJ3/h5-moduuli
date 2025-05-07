# NGINX - Event Driven Automation (SaltStack Module)

This SaltStack module automates the setup and monitoring of an nginx service.
It installs and configures nginx, sets up a Salt beacon to monitor its status.
It uses Salt reactor to automatically restart nginx if it stops.

![framework](https://github.com/HMJ3/h5-moduuli/blob/main/framework.png)

img source: ([Salt Project](https://docs.saltproject.io/salt/user-guide/en/latest/topics/beacons.html))

Detailed report (in finnish) here: https://github.com/HMJ3/linux-course/blob/main/assignments/h5.md

---

## Setup

**1. Create a new directory called "salt"**

<pre>
$ sudo mkdir /srv/salt && cd /srv/salt
</pre>

**2. Clone the repository**

<pre>
$ sudo git clone https://github.com/HMJ3/h5-moduuli.git
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

---

**Or you can run all commands at once:**

```
sudo mkdir -p /srv/salt && cd /srv/salt && \
sudo git clone https://github.com/HMJ3/h5-moduuli.git && \
sudo mv h5-moduuli/reactor/reactor.conf /etc/salt/master.d/ && \
sudo systemctl restart salt-master.service
```

**Call salt state**
```
sudo salt '*' state.apply h5-moduuli
```

---

**Other commands**

Monitor event-buss:

```
sudo salt-run state.event pretty=True
```


