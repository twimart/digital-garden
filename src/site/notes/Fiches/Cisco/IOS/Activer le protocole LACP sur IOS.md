---
{"dg-publish":true,"permalink":"/fiches/cisco/ios/activer-le-protocole-lacp-sur-ios/"}
---


Voici comment activer et configurer Etherchannel entre 2 switch, comme-ci dessous:

![reseau lacp.png](/img/user/Images/reseau%20lacp.png)

- Configurer *SW1* de la manière suivante: 

```
SW1(config)#interface range GigabitEthernet 0/1 - 2
SW1(config-if-range)#channel-group 1 mode active 
```

- et *SW2* de la manière suivante:

```
SW2(config)#interface range GigabitEthernet 0/1 - 2
SW2(config-if-range)#channel-group 1 mode passive 
```

On peut ensuite vérifier la configuration avec les commandes suivantes:

	show etherchannel 1 port-channel

et

	show interfaces GigabitEthernet 0/1 etherchannel



