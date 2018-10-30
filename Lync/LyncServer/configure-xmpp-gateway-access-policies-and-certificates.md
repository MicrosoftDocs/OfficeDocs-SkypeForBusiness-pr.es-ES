---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
TOCTitle: Configurar certificados y directivas de acceso por puerta de enlace XMPP
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49889826
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar certificados y directivas de acceso por puerta de enlace XMPP

 

_**Última modificación del tema:** 2012-10-15_

La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios de Lync acceder a usuarios del dominio XMPP mediante:

  - Mensajería instantánea y presencia: solo persona a persona

  - Creación de contactos federados de XMPP en el cliente Lync

Cuando se configuran directivas para la compatibilidad con socios federados del protocolo extensible de mensajería y presencia (XMPP), las directivas se aplican únicamente a usuarios de dominios XMPP federados, pero no a usuarios de los proveedores de servicios de mensajería instantánea (MI) mediante el protocolo de inicio de sesión (SIP) (como pueda ser Windows Live) ni dominios federados de SIP. Configure un socio federado de XMPP para cada dominio federado de XMPP a los que desee permitir que los usuarios agreguen contactos y con los que se puedan comunicar. Una vez incorporadas las directivas, necesitará configurar los certificados de puerta de enlace XMPP.


> [!NOTE]
> Para comenzar con la migración de la puerta de enlace XMPP, necesitará implementar la puerta de enlace XMPP de Lync Server 2013 y configurar directivas de acceso para permitir a los usuarios el uso de la puerta de enlace XMPP de Lync Server 2013. Se deberán mover todos los usuarios a la implementación de Lync Server 2013 antes de llevar a cabo estos pasos. Si desea información detallada, vea <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configurar una puerta de enlace XMPP en Lync Server 2013</A>.



## Configuración de una directiva de acceso externo para permitir a los usuarios el uso de la puerta de enlace XMPP de Lync Server 2013

1.  Abra Panel de control de Lync Server.

2.  En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, a continuación, en **Directiva de acceso externo**.

3.  Haga clic en **Nuevo** y en **Directiva de usuario**.

4.  Escriba un nombre para la directiva de usuario de acceso externo.

5.  Proporcione una descripción de la directiva de usuario de acceso externo.

6.  Seleccione **Habilitar comunicaciones con usuarios federados**.

7.  Seleccione **Habilitar comunicaciones con usuarios federados XMPP**.

8.  Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o usuario.

