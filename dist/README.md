# Build

Before starting the build, you need the following tools installed in your machine:

- npm
- golang

Then prepare the sources and start the build (using NethServer build system):

```
./prep-sources && makerpms dante.spec
```

# Installation

After installing all RPMs, make sure to:

1. Enable virgilio server:
   ```
   systemctl enable --now virgilio
   ```

2. Execute all miners at least once:
   ```
   ciacco
   ```

3. Generate the mail and send it to root:
   ```
   cd /usr/share/dante/caronte && ./caronte 'http://localhost:9292/#/?theme=dark&palette=palette3&last=week&lang=en' root@localhost
   ```

4. To access the web interface:
   ```
   ln -s /usr/share/dante/beatrice /var/www/html
   ```

Configuration files:

- `/etc/sysconfig/dante`
- `/etc/cron.d/dante`
