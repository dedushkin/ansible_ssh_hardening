Ansible SSH hardening
=========

Configure SSH daemon with secure settings, fail2ban and Telegram login notifications

Role Variables
--------------

| Variable | Default value | Description and example |
| -------- | ------------- | ----------------------- |
| ssh_hardening_max_auth_tries | 3 | MaxAuthTries |
| ssh_hardening_allowed_users | `{{ ansible_user }}` | AllowUsers |
| ssh_hardening_client_alive_interval | 300 | ClientAliveInterval |
| ssh_hardening_client_alive_count_max | 2 | ClientAliveCountMax |
| ssh_hardening_host_key_algorithms | ssh-ed25519,rsa-sha2-512,rsa-sha2-256 | HostKeyAlgorithms | 
| ssh_hardening_kex_algorithms | curve25519-sha256@libssh.org,ecdh-sha2-nistp521,ecdh-sha2-nistp384,ecdh-sha2-nistp256 | KexAlgorithms |
| ssh_hardening_ciphers | chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes128-gcm@openssh.com | Ciphers |
| ssh_hardening_macs | hmac-sha2-512-etm@openssh.com,hmac-sha2-256-etm@openssh.com | MACs |
| ssh_hardening_enable_fail2ban | true | Install and configure fail2ban |
| ssh_hardening_fail2ban_maxretry | 3 | Max attempts before ban |
| ssh_hardening_fail2ban_findtime | 10m | Time window for failed attempts check | 
| ssh_hardening_fail2ban_bantime | 1h | Ban duration |
| ssh_hardening_enable_tg_notifications | true | Configure Telegram notifications on login |
| ssh_hardening_tg_notifications_bot_token | changeme:changeme | Telegram bot token |
| ssh_hardening_tg_notifications_chat_id | changeme | Telegram chat ID |
| ssh_hardening_tg_notifications_timezone | Asia/Tbilisi | Timezone |

Example Playbook
----------------

```
- name: Prepare server
  hosts: all
  become: true
  roles:
    - ssh_hardening
```

License
-------

Copyright 2026 Vladislav Dedushkin

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS “AS IS” AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

Author Information
------------------

Telegram: [@vlad_dedushkin](https://t.me/vlad_dedushkin)