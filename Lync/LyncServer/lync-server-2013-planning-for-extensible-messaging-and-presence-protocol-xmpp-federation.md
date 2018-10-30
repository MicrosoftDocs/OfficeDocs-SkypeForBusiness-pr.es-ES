---
title: "Planificar federac. protoc. extensible de mensajería y presencia en Lync Server 2013"
TOCTitle: "Plan. de féd. XMPP (Extensible Messaging and Presence Protocol) dans LS 2013"
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48276061
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeación de federación de protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-22_

Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace del protocolo extensible de mensajería y presencia (XMPP) que podía implementarse como un rol de servidor independiente para permitir la federación con las implementaciones de XMPP. En Microsoft Lync Server 2013, la funcionalidad de XMPP se puede implementar como una característica. La funcionalidad de XMPP se instala en dos partes: un proxy XMPP que se ejecuta en el Servidor perimetral y la puerta de enlace XMPP que se ejecuta en los Servidores front-end

La implementación y configuración de XMPP se trata en [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md). La planeación para admitir XMPP en su organización se realiza mediante la definición de reglas de puerto y protocolo en el firewall, la configuración de certificados y la adición de registros DNS. Las tablas siguientes resumen la información que necesita para implementar correctamente la federación de XMPP para su implementación.

> [!IMPORTANT]  
> La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



## En esta sección

  - [Resumen de certificado - Federación del Protocolo extensible de mensajería y presencia (XMPP)](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Resumen de puertos - Federación del protocolo extensible de mensajería y presencia (XMPP)](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Resumen de DNS - Federación del Protocolo extensible de mensajería y presencia (XMPP)](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

## Vea también

#### Tareas

[Configurar la federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  

#### Otros recursos

[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsXmppAllowedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppAllowedPartner)  
[Get-CsXmppGatewayConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppGatewayConfiguration)

