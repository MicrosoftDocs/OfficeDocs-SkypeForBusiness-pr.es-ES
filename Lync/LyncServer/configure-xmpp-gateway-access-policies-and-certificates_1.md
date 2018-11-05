---
title: Configurar las directivas y los certificados de acceso a puertas de enlace XMPP
TOCTitle: Configurar las directivas y los certificados de acceso a puertas de enlace XMPP
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49889689
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar las directivas y los certificados de acceso a puertas de enlace XMPP

 

_**Última modificación del tema:** 2012-10-15_

La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios de Lync acceder a usuarios del dominio XMPP mediante:

  - Mensajería instantánea y presencia: solo persona a persona

  - Creación de contactos federados de XMPP en el cliente Lync

Cuando se configuran directivas para la compatibilidad con socios federados del protocolo extensible de mensajería y presencia (XMPP), las directivas se aplican únicamente a usuarios de dominios XMPP federados, pero no a usuarios de los proveedores de servicios de mensajería instantánea (MI) mediante el protocolo de inicio de sesión (SIP) (como pueda ser Windows Live) ni dominios federados de SIP. Configure un socio federado de XMPP para cada dominio federado de XMPP a los que desee permitir que los usuarios agreguen contactos y con los que se puedan comunicar. Una vez incorporadas las directivas, necesitará configurar los certificados de puerta de enlace XMPP.


> [!NOTE]
> Para comenzar con la migración de la puerta de enlace XMPP, necesitará implementar la puerta de enlace XMPP de Lync Server 2013 y configurar directivas de acceso para permitir a los usuarios el uso de la puerta de enlace XMPP de Lync Server 2013. Se deberá mover todos los usuarios a la implementación de Lync Server 2013 antes de llevar a cabo estos pasos. Si desea información detallada, consulte <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configurar la puerta de enlace XMPP en Lync Server 2013</A>.



## Configuración de una directiva de acceso externo para permitir a los usuarios el uso de la puerta de enlace XMPP de Lync Server 2013

1.  Abra Panel de control de Lync Server.

2.  En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y, a continuación, en **Directiva de acceso externo**.

3.  Haga clic en **Nuevo** y en **Directiva de usuario**.

4.  Escriba un nombre para la directiva de usuario de acceso externo.

5.  Proporcione una descripción de la directiva de usuario de acceso externo.

6.  Seleccione **Habilitar comunicaciones con usuarios federados**.

7.  Seleccione **Habilitar comunicaciones con usuarios federados XMPP**.

8.  Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o usuario.

