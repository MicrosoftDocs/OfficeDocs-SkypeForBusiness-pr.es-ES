---
title: 'Lync Server 2013: Planeación de líneas telefónicas privadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8051fc18fd42c2c9773d4e0b8904f2923687fe2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>Planeación de líneas telefónicas privadas con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-11_

Lync Server 2013 introduce la capacidad de proporcionar a los usuarios una segunda línea de teléfono privada además de la línea de teléfono principal. Las líneas de teléfono privadas suelen asignarse a ejecutivos y a otros usuarios que desean un número de teléfono privado en el que se les pueda contactar directamente.

Las líneas de teléfono privadas solo pueden configurarse con el shell de administración de Lync Server. No puede configurar líneas telefónicas privadas con el panel de control de Lync Server. Las líneas de teléfono privadas solo deben configurarse en implementaciones de Lync Server y no en implementaciones mixtas.

<div>

## <a name="characteristics-of-private-telephone-lines"></a>Características de las líneas de teléfono privadas

A pesar de que el concepto de poseer una segunda línea de teléfono privada es bastante sencillo, es importante conocer las características de las líneas privadas, así como las similitudes y las diferencias con respecto a las líneas de teléfono principales de los usuarios.

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>Características generales de las líneas de teléfono privadas

  - Un usuario solo puede tener una línea de teléfono privada.

  - Los usuarios con una línea de teléfono privada solo disponen de un buzón de correo de voz y reciben notificaciones de llamadas perdidas en una única dirección de correo electrónico.

  - Los usuarios con una línea de teléfono privada no disponen de una segunda dirección SIP y una segunda línea de teléfono privada no proporciona al usuario una segunda presencia en la red (como una segunda identidad de mensajería instantánea).

  - Las líneas de teléfono privadas solo están disponibles para implementaciones locales. No están disponibles en las implementaciones hospedadas de Lync Server.

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Diferencias entre las líneas de teléfono privadas y las líneas de teléfono principales

  - Los números de teléfono de las líneas de teléfono privadas no aparecen en los directorios de teléfonos ni en las listas de contactos que se obtienen de Servicios de dominio de Active Directory.

  - Ninguna de las siguientes características está disponible con una línea de teléfono privada: desvío de llamadas, llamada de equipo, delegación, anillo de equipo, recogida de llamada de grupo y aplicación de grupo de respuesta.

  - Las llamadas realizadas a una línea de teléfono privada suenan de una forma especial y la notificación del sistema para la llamada indica al usuario que la llamada entrante proviene de su línea privada.

  - Las llamadas realizadas a la línea de teléfono privada siempre suenan. No siguen las reglas de "no molestar".

  - Las líneas de teléfono privadas son solo entrantes y no pueden usarse para realizar llamadas salientes. Cuando un usuario con una línea de teléfono privada realiza una llamada, esta se realiza desde la línea de teléfono principal del usuario y no se oculta el nombre del usuario ni el número teléfono principal del usuario a la persona que recibe la llamada.

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre las líneas de teléfono privadas y las líneas de teléfono principales

  - Las llamadas no respondidas realizas a una línea de teléfono privada se enrutan a la misma bandeja de entrada de correo de voz de la línea telefónica principal (si el correo de voz está habilitado).

  - El estacionamiento de llamadas y la atención de llamadas funcionan con las líneas de teléfono privadas exactamente de la misma forma que con la línea de teléfono principal del usuario.

  - Cuando las llamadas simultáneas se habilitan en una línea de teléfono principal del usuario, también se habilitan en la línea de teléfono privada.

  - El número de teléfono de una línea de teléfono privada se conserva en el registro de detalles de llamadas de la misma forma que el número de teléfono de una línea de teléfono principal del usuario, pero con una indicación para advertir que se trata de un número de teléfono privado.

  - Después de que un usuario responda a una llamada en una línea de teléfono privada, la llamada se trata de la misma forma que una llamada en la línea de teléfono principal del usuario. Por ejemplo, si un usuario que recibe una llamada en una línea de teléfono privada reenvía la llamada o invita a otros a una llamada de conferencia, el nombre del usuario aparece en Lync 2013 y el número de teléfono de la línea de teléfono principal del usuario aparece en identificador de llamada.

  - Los usuarios pueden desviar una llamada de la línea de teléfono privada (redirigir la llamada a otro destino, como un teléfono móvil o un teléfono particular, antes de responder) de la misma forma que con una línea de teléfono principal.
    
    <div>
    

    > [!NOTE]  
    > Cuando una llamada a una línea privada se enruta a un número de teléfono alternativo, el número de teléfono de la línea de teléfono privada se pone a disposición del número de teléfono alternativo y puede mostrarse en los registros de dicho número.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Las llamadas realizadas desde una conferencia a la línea de teléfono privada no tendrán la indicación <EM>línea privada</EM> en la notificación entrante del sistema.

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>Administración de líneas de teléfono privadas

Además de los aspectos técnicos de la creación y administración de líneas de teléfono privadas, tendrá que establecer procedimientos administrativos. Entre estos, se incluye la determinación de directivas para indicar qué personas de la organización pueden obtener una línea privada, la creación y administración de listas de personas y sus líneas de teléfono (porque los números de teléfono de líneas privadas no se almacenan en Active Directory), la posible creación de un directorio de teléfonos privados para ejecutivos, la preparación de formación para usuarios y otras tareas relacionadas.

<div>


> [!NOTE]  
> La línea telefónica privada se almacena en Active Directory como un atributo msRTCSIP-PrivateLine en el objeto de usuario. De forma predeterminada los miembros del grupo Usuarios autenticados tiene acceso de lectura para este atributo.



</div>

<div>

## <a name="assigning-telephone-numbers"></a>Asignación de números de teléfono

Las cuentas para nuevos usuarios que necesitan líneas de teléfono privadas se crean de la misma forma que las cuentas sin líneas de teléfono privadas, mediante el panel de control de Lync Server o el shell de administración de Lync Server.

Use el cmdlet **set-CsUser** en el shell de administración de Lync Server para asignar un número de teléfono a una línea de teléfono privada para un usuario, por ejemplo, **set-CsUser-Identity "SIP:Joe@contoso.com"-PrivateLine "Tel: + 14255551212"**.

Los números de teléfono de las líneas de teléfono privadas pueden tener entre 3 y 15 números de longitud y deben ir precedidos del prefijo "TEL:". Pueden tener cualquier código de área y de país, siempre que la organización disponga de llamada directa a la extensión para dicho código de área y de país/región.

Para obtener más información acerca de los cmdlets y el shell de administración de Lync Server, consulte la documentación del [Shell de administración de Lync server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>Líneas de teléfono privadas en implementaciones mezcladas

Las líneas de teléfono privadas solo deben configurarse para implementaciones de Lync Server. En una implementación en la que hay servidores de Lync Server y Office Communications Server 2007 o de Office Communications Server 2007 R2, cuando un usuario de una versión anterior intenta llamar a una línea de teléfono privada, se produce un error en el enrutamiento de la llamada porque el servidor no puede realizar una búsqueda inversa de números en una línea de teléfono privada.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

