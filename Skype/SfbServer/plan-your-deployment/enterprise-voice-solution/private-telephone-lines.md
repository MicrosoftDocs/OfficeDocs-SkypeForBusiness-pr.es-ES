---
title: Planear líneas telefónicas privadas con Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planificación de líneas de teléfono privadas (secundarias) en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 38dd81bb0fae9f7edd062e111db462d264dda1d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276563"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planear líneas telefónicas privadas con Skype empresarial
 
Planificación de líneas de teléfono privadas (secundarias) en Skype empresarial Server Enterprise Voice.
  
Skype empresarial Server le permite dar a los usuarios una segunda línea telefónica privada, además de la línea telefónica principal. Las líneas de teléfono privadas suelen asignarse a ejecutivos y a otros usuarios que desean un número de teléfono privado en el que se les pueda contactar directamente.
  
Las líneas de teléfono privadas solo se pueden configurar con el shell de administración de Skype empresarial Server. No puede configurar líneas telefónicas privadas con el panel de control de Skype empresarial Server. Las líneas de teléfono privadas solo se deben configurar en implementaciones de Skype empresarial Server y no en implementaciones mixtas.
  
## <a name="characteristics-of-private-telephone-lines"></a>Características de las líneas de teléfono privadas

A pesar de que el concepto de una segunda línea telefónica privada es fundamentalmente simple, es importante comprender las características de las líneas privadas y las formas en las que son similares a las líneas de teléfono principales de los usuarios y las diferencias entre ellas.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Características generales de las líneas de teléfono privadas

- Un usuario solo puede tener una línea de teléfono privada.
    
- Los usuarios con una línea de teléfono privada solo disponen de un buzón de correo de voz y reciben notificaciones de llamadas perdidas en una única dirección de correo electrónico.
    
- Los usuarios con una línea de teléfono privada no disponen de una segunda dirección SIP y una segunda línea de teléfono privada no proporciona al usuario una segunda presencia en la red (como una segunda identidad de mensajería instantánea). 
    
- Las líneas de teléfono privadas solo están disponibles para implementaciones locales. No están disponibles con implementaciones hospedadas de Skype empresarial Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Diferencias entre las líneas de teléfono privadas y las líneas de teléfono principales

- Los números de teléfono de las líneas de teléfono privadas no aparecen en los directorios de teléfonos ni en las listas de contactos que se obtienen de Servicios de dominio de Active Directory.
    
- Ninguna de las características siguientes está disponible con una línea de teléfono privada: desvío de llamadas, llamada de equipo, delegación, respuesta de llamadas en grupo y la aplicación Grupo de respuesta.
    
- Las llamadas realizadas a una línea de teléfono privada suenan de una forma especial y la notificación del sistema para la llamada indica al usuario que la llamada entrante proviene de su línea privada.
    
- Las llamadas realizadas a la línea de teléfono privada siempre suenan. No siguen las reglas de "no molestar".
    
- Las líneas de teléfono privadas son solo entrantes y no pueden usarse para realizar llamadas salientes. Cuando un usuario con una línea telefónica privada hace una llamada, la llamada se origina desde la línea de teléfono principal del usuario y no oculta el nombre del usuario o el número de teléfono principal del usuario de la persona a la que llama.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre las líneas de teléfono privadas y las líneas de teléfono principales

- Las llamadas no respondidas realizas a una línea de teléfono privada se redirigen a la misma bandeja de entrada de correo de voz de la línea telefónica principal (si el correo de voz está habilitado).
    
- El servicio de llamada y la recogida de llamadas funcionan con líneas de teléfono privadas exactamente de la misma manera que lo hacen con la línea de teléfono principal del usuario.
    
- Cuando se habilitan las llamadas simultáneas en la línea telefónica principal de un usuario, también se habilita en la línea telefónica privada.
    
- El número de teléfono de una línea telefónica privada se registra en el registro de detalles de la llamada de la misma manera que el número de teléfono de la línea telefónica principal de un usuario, pero con una indicación de que es un número de teléfono privado.
    
- Después de que un usuario responde a una llamada en una línea telefónica privada, la llamada se trata de la misma forma que una llamada en la línea de teléfono principal del usuario. Por ejemplo, si un usuario que recibe una llamada en una línea telefónica privada reenvía la llamada o invita a otras personas a una llamada de conferencia, el nombre del usuario aparece en Skype empresarial y el número de teléfono de la línea de teléfono principal del usuario aparece en la identificación de llamadas.
    
- Los usuarios pueden desviar una llamada de la línea de teléfono privada (redirigir la llamada a otro destino, como un teléfono móvil o un teléfono particular, antes de responder) de la misma forma que con una línea de teléfono principal. 
    
    > [!NOTE]
    > Cuando una llamada a una línea privada se redirige a un número de teléfono alternativo, el número de teléfono de la línea de teléfono privada se pone a disposición del número de teléfono alternativo y puede mostrarse en los registros de dicho número. 
  
    > [!NOTE]
    > Las llamadas desde una conferencia a la línea telefónica privada no tendrán una indicación de *línea privada* en la notificación del sistema entrante.
  
## <a name="administering-private-telephone-lines"></a>Administración de líneas de teléfono privadas

Además de los aspectos técnicos de la creación y administración de líneas de teléfono privadas, tendrás que establecer procedimientos administrativos. Entre estos, se incluye la determinación de directivas para indicar qué personas de la organización pueden obtener una línea privada, la creación y administración de listas de personas y sus líneas de teléfono, la posible creación de un directorio de teléfonos privados para ejecutivos, la preparación de formación para usuarios y otras tareas relacionadas.
  
> [!NOTE]
> La línea telefónica privada se almacena en Active Directory como un atributo msRTCSIP-PrivateLine en el objeto de usuario. De forma predeterminada, los miembros del grupo Usuarios autenticados tienen acceso de lectura para este atributo. 
  
### <a name="assigning-telephone-numbers"></a>Asignar números de teléfono

 Las cuentas de los nuevos usuarios que necesiten líneas de teléfono privadas se crean de la misma manera que las cuentas sin líneas de teléfono privadas, mediante el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial.
  
Use el cmdlet **set-CsUser** en el shell de administración de Skype empresarial Server para asignar un número de teléfono a una línea telefónica privada para un usuario, por ejemplo, **set-CsUser-Identity "SIP:Joe@contoso.com"-PrivateLine "Tel: + 14255551212"**.
  
Los números de teléfono de las líneas telefónicas privadas pueden tener entre 3 y 15 números de longitud y deben ir precedidos del prefijo "TEL:". Pueden tener cualquier código de área y de país, siempre que la organización disponga de llamada directa a la extensión para dicho código de área y de país o región. 
  
Para obtener más información sobre los cmdlets y el shell de administración de Skype empresarial Server, consulte la documentación del shell de administración de Skype empresarial.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Líneas de teléfono privadas en implementaciones combinadas

Las líneas de teléfono privadas solo deben configurarse para implementaciones de Skype empresarial Server o Lync Server 2013. En una implementación en la que hay servidores que ejecutan versiones anteriores de Lync Server, cuando un usuario de una versión anterior intenta llamar a una línea telefónica privada, se produce un error en el enrutamiento de la llamada porque el servidor no puede realizar una búsqueda de números invertidas en una línea telefónica privada.
  

