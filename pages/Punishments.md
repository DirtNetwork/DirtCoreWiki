### Index

* [Punishments](#punishments)
    * [Ban](#ban)
    * [IP Ban](#ip-ban)
    * [Kick](#kick)
    * [Mute](#mute)
    * [Unban](#unban)
    * [IP Unban](#ip-unban)
    * [Unmute](#unmute)
    * [Warn](#warn)

___

# Punishments

A punishment is the infliction or imposition of a penalty.

All punishments are structured the following way:

* **Incident ID**: An 8 character long unique ID associated with the punishment. The incident ID for DirtCraft always
  starts with `DC`, e.g. `DCA1B2C3`. It is oftentimes prefixed by a `#`, e.g. `#DCA1B2C3`.
* **Timestamp**: A exact time a punishment has been issued, e.g. `2024-05-27 01:44:50`.
* **Target**: The UUID of the target, e.g. `ca236e76-904b-4e34-a62e-f90bc13e3ead`.
* **Author**: The UUID of the author,e.g. `ca236e76-904b-4e34-a62e-f90bc13e3ead`, `00000000-0000-0000-0000-000000000000`
  in case the punishment was issued via console.
* **Reason**: The reason for the punishment.
* **Server**: The server the punishment was issued on.

## Ban

Bans prevent users from entering the network.

Bans have the following additional fields:

* **Expiry**: The expiry of the ban, e.g. `2024-05-27 01:45:00`. Will be `NULL` in case of a permanent ban.
* **History**: The history of the ban.
* **Unban**: The unban associated with this ban. Will be `NULL` if no unban is present.
* **IP Ban**: If the ban is an IP ban. Will be either `true` or `false`.

![](../img/tempban.png)

Related:

* [/ban \<target\> [reason...]](Punishment-Commands#ban-target-reason)
* [/tempban \<target\> \<time\> \<d|h|m|s\> [reason...]](Punishment-Commands#tempban-target-time-dhms-reason)

## IP Ban

If a ban is marked as an IP ban, the network will be scanned for online users with IP history matches.
If there is a match, the user will be kicked from the server.

Upon login, the IP history will be crosschecked for IP history entries of users with active IP bans.
If there is a match, the user will be prevented from entering the network.

Related: [/ban-ip \<target\> [reason...]](Punishment-Commands#ban-ip-target-reason)

## Kick

Kicks disconnect users from the network once.

Kicks do not have additional fields.

Related: [/kick \<target\> [reason...]](Punishment-Commands#kick-target-reason)

## Mute

Mutes prevent users from writing chat messages or commands associated with writing chat messages.

Mutes have the following additional fields:

* **Expiry**: The expiry of the mute, e.g. `2024-05-27 01:45:00`. Will be `NULL` in case of a permanent mute.
* **History**: The history of the mute.
* **Unmute**: The unmute associated with this ban. Will be `NULL` if no unmute is present.

Related:

* [/mute \<target\> [reason...]](Punishment-Commands#mute-target-reason)
* [/tempmute \<target\> \<time\> \<d|h|m|s\> [reason...]](Punishment-Commands#tempmute-target-time-dhms-reason)

## Unban

Unbans end the current ban and enable users to enter the network again.

Unbans have the following additional fields:

* **Reverts**: The ban this unban is associated to.

Related: [/unban \<target\> [reason...]](Punishment-Commands#unban-target-reason)

## IP Unban

IP Unbans mark a ban as a non-IP ban.

Related: [/unban-ip \<target\> [reason...]](Punishment-Commands#unban-ip-target-reason)

## Unmute

Unmutes end the current mute and enable users to take part in chat activities.

Unmutes have the following additional fields:

* **Reverts**: The mute this unmute is associated to.

Related: [/unmute \<target\> [reason...]](Punishment-Commands#unmute-target-reason)

## Warn

Warns notify users of their wrongdoings. If a warn is issued while the user is offline, the user will be notified the
next time they enter the network.

Warns do not have additional fields.

Related: [/warn \<target\> \<reason...\>](Punishment-Commands#warn-target-reason)
