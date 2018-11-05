---
title: 'Lync Server 2013: Componentes y topologías para mensajería unificada local'
TOCTitle: Componentes y topologías para mensajería unificada local
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48274680
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes y topologías para mensajería unificada local en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-25_

En este tema se describen los componentes de Microsoft Exchange Server 2013 necesarios para proporcionar características de Mensajería unificada de Exchange (UM) a la implementación de Lync Server 2013. También se describen las topologías admitidas para la integración local de Mensajería unificada de Exchange.

## Componentes de Exchange Server

Para proporcionar las características y los servicios de Mensajería unificada de Exchange descritos en [Características de la mensajería unificada integrada y Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) a los usuarios de Telefonía IP empresarial de su organización, debe implementar un servidor de buzón de Microsoft Exchange y un servidor de acceso de cliente, que hospeda buzones de usuario y proporciona una ubicación de almacenamiento único para correo electrónico y correo de voz. Mensajería unificada de Exchange se ejecuta como un servicio en el buzón de Exchange y los servidores de acceso de cliente.

Para obtener detalles acerca de los componentes de MU de Exchange en Microsoft Exchange Server 2007 y Microsoft Exchange Server 2010, vea [Implementar la mensajería unificada de Exchange local para proporcionar correo de voz de Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) en la documentación de implementación.

## Topologías admitidas

Puede implementar Lync Server 2013 y Mensajería unificada de Exchange (UM) en el mismo bosque o en varios bosques. Si la implementación se extiende por varios bosques, deberá seguir los pasos necesarios para la integración de Exchange en cada bosque de Mensajería unificada de Exchange. Es más, deberá configurar cada bosque de Microsoft Exchange de forma que confíe en el bosque de Lync Server 2013 y el bosque Lync Server 2013 de forma que confíe en el bosque de Mensajería unificada de Exchange. Además de esta confianza de bosques, la configuración de Mensajería unificada de Exchange para todos los usuarios debe establecerse en los objetos de usuario del bosque de Lync Server 2013.

Lync Server 2013 admite las siguientes topología para la integración de Mensajería unificada de Exchange:

  - Bosque único

  - Dominio único (es decir, un único bosque con un único dominio). Lync Server 2013, Microsoft Exchange y los usuarios residen en el mismo dominio.

  - Varios dominios (es decir, un dominio raíz con uno o más dominios secundarios). Los servidores de Lync Server 2013 y Microsoft Exchange se implementan en otros dominios distintos al dominio en el que se han creado usuarios. Los servidores de Mensajería unificada de Exchange pueden implementarse en dominios diferentes del grupo de servidores de Lync Server 2013 admitido.

  - Varios bosques (es decir, un bosque de recursos). Lync Server 2013 se implementa en un único bosque y, a continuación, se distribuyen los usuarios por varios bosques. Los atributos de usuarios de mensajería instantánea de Exchange deben replicarse en el bosque de Lync Server 2013.
    

    > [!NOTE]
    > Exchange se puede implementar en varios bosques. Cada organización de Exchange puede proporcionar Mensajería unificada de Exchange a sus usuarios, o bien se pueden implementar Mensajería unificada de Exchange en el mismo bosque que Lync Server 2013.


