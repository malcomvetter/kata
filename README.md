# Breach Kata
[Kata](https://en.wikipedia.org/wiki/Kata) are a single unit of choreographed movements that are trained repetitively in martial arts so the student can acquire mastery of the art.  This term has also been applied to [programming](https://en.wikipedia.org/wiki/Kata_(programming)) ([cyber dojo](http://cyber-dojo.org/)).  In this context, these kata are for steps in the exploit chain of a network breach (i.e. red teaming or penetration testing).

These are single units of movement that should become second nature for the penetration tester. These could also make good basic technical interview questions for a red team role.

To perform the kata, have a training partner setup a lab environment using a variation discussed below and execute the sequence.

## Post-Exploitation
### Persistence

1.	Establish in-memory persistence from a shell that opens in an ephemeral process which dies within 5 seconds. Practice variations include: Operating Systems (Windows, *nix, Mac) and context (userland vs privileged).
2.	Establish on-disk persistence from a currently stable in-memory shell. Practice variations include: Operating System (Windows, *nix, Mac), context (userland vs privileged), and available writable directories (e.g. suppose the primary partition is full or unresponsive).
3.	Establish a secondary communications channel (different from the currently executing shell on the target host). Practice Variations include: host role (Server vs. User endpoint/desktop), Operating System (Windows, *nix, Mac) and egress traffic filtering policies, for example: (let creativity be the limit) all outbound traffic permitted, TCP port 443 outbound without protocol validation, HTTPS full proxy decryption, etc.

### Lateral Movement

4.	Move from Windows host A to Windows host B. Variations include protocol (RDP, SMB, WMI, etc.) and vulnerability exploitation (e.g. MS08-067, pass the hash).
5.	Move from Windows host A to Linux host B. Variations include protocol (e.g. SSH, SMB, NFS, etc.)
6.	Move from Linux host A to Windows host B. Variations include protocol (e.g. SMB/RPC, RDP) and vulnerability exploitation.
7.	Move from Mac desktop host A to a secondary host B. Variations include target OS (Windows, *nix, another Mac) and protocol.

### Privilege Escalation
8.	Within the OS, escalate from a userland process to administrator. Variations include OS (Windows, *nix, Mac), discovered credentials, UAC Bypass, file permissions, service misconfiguration, etc.
9.	Within an application, escalate from user to admin. Variations include client side policy enforcement, forced browsing, direct object reference, information leak, XSS/CSRF an administrator, etc.
10.	Within an enterprise network, escalate from single host to many.  Variations include credential discovery (e.g. Mimikatz, internal CA certificate, admin password in text file, social engineer an administrator while keylogging, etc.), vulnerability exploitation (missing patch, misconfigured file permissions), and detection controls in play.

