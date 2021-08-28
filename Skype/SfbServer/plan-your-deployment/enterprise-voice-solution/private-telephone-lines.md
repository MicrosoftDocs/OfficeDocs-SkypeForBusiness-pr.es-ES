---
title: Planeación de líneas telefónicas privadas con Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planeación de líneas telefónicas privadas (secundarias) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 3f682d6d150bd52093d8c7bbb050b53b95ac3125
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603849"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planeación de líneas telefónicas privadas con Skype Empresarial
 
Planeación de líneas telefónicas privadas (secundarias) en Skype Empresarial Server Telefonía IP empresarial.
  
Skype Empresarial Server permite proporcionar a los usuarios una segunda línea de teléfono privada además de su línea de teléfono principal. Las líneas de teléfono privadas suelen asignarse a ejecutivos y a otros usuarios que desean un número de teléfono privado en el que se les pueda contactar directamente.
  
Las líneas telefónicas privadas solo se pueden configurar con el Shell Skype Empresarial Server administración. No puede configurar líneas telefónicas privadas con el panel Skype Empresarial Server control. Las líneas telefónicas privadas solo deben configurarse en implementaciones de Skype Empresarial Server y no en implementaciones mixtas.
  
## <a name="characteristics-of-private-telephone-lines"></a>Características de las líneas de teléfono privadas

Aunque el concepto de una segunda línea telefónica privada es fundamentalmente sencillo, es importante comprender las características de las líneas privadas y las formas en que son similares y diferentes de las líneas telefónicas principales de los usuarios.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Características generales de las líneas de teléfono privadas

- Un usuario solo puede tener una línea de teléfono privada.
    
- Los usuarios con una línea de teléfono privada solo disponen de un buzón de correo de voz y reciben notificaciones de llamadas perdidas en una única dirección de correo electrónico.
    
- Los usuarios con una línea de teléfono privada no disponen de una segunda dirección SIP y una segunda línea de teléfono privada no proporciona al usuario una segunda presencia en la red (como una segunda identidad de mensajería instantánea). 
    
- Las líneas de teléfono privadas solo están disponibles para implementaciones locales. No están disponibles con implementaciones hospedadas de Skype Empresarial Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Diferencias entre las líneas de teléfono privadas y las líneas de teléfono principales

- Los números de teléfono de las líneas de teléfono privadas no aparecen en los directorios de teléfonos ni en las listas de contactos que se obtienen de Servicios de dominio de Active Directory.
    
- Ninguna de las siguientes características está disponible con una línea telefónica privada: reenvío de llamadas, llamada de equipo, delegación, anillo de grupo, recogida de llamadas en grupo y aplicación de grupo de respuesta.
    
- Las llamadas realizadas a una línea de teléfono privada suenan de una forma especial y la notificación del sistema para la llamada indica al usuario que la llamada entrante proviene de su línea privada.
    
- Las llamadas realizadas a la línea de teléfono privada siempre suenan. No siguen las reglas de "no molestar".
    
- Las líneas de teléfono privadas son solo entrantes y no pueden usarse para realizar llamadas salientes. Cuando un usuario con una línea de teléfono privada realiza una llamada, la llamada se origina desde la línea de teléfono principal del usuario y no oculta el nombre del usuario o el número de teléfono principal del usuario de la persona a la que se llamó.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre las líneas de teléfono privadas y las líneas de teléfono principales

- Las llamadas no respondidas realizas a una línea de teléfono privada se enrutan a la misma bandeja de entrada de correo de voz de la línea telefónica principal (si el correo de voz está habilitado).
    
- El estacionamiento de llamadas y el trabajo de recogida de llamadas con líneas telefónicas privadas se hacen exactamente de la misma manera que con la línea de teléfono principal del usuario.
    
- Cuando la llamada simultánea está habilitada en la línea de teléfono principal de un usuario, también se habilita en la línea telefónica privada.
    
- El número de teléfono de una línea telefónica privada se registra en el registro de detalles de llamada de la misma manera que el número de teléfono de la línea de teléfono principal de un usuario, pero con una indicación de que es un número de teléfono privado.
    
- Después de que un usuario responda a una llamada en una línea telefónica privada, la llamada se tratará igual que una llamada en la línea de teléfono principal del usuario. Por ejemplo, si un usuario que recibe una llamada en una línea telefónica privada reenvía la llamada o invita a otros usuarios a una llamada de conferencia, el nombre del usuario aparece en Skype Empresarial y el número de teléfono de la línea de teléfono principal del usuario aparece en el identificador de autor de la llamada.
    
- Los usuarios pueden desviar una llamada de la línea de teléfono privada (redirigir la llamada a otro destino, como un teléfono móvil o un teléfono particular, antes de responder) de la misma forma que con una línea de teléfono principal. 
    
    > [!NOTE]
    > Cuando una llamada a una línea privada se enruta a un número de teléfono alternativo, el número de teléfono de la línea de teléfono privada se pone a disposición del número de teléfono alternativo y puede mostrarse en los registros de dicho número. 
  
    > [!NOTE]
    > Las llamadas de una conferencia a la  línea telefónica privada no tendrán una indicación de línea privada en la notificación del sistema entrante.
  
## <a name="administering-private-telephone-lines"></a>Administración de líneas de teléfono privadas

Además de los aspectos técnicos de la creación y administración de líneas de teléfono privadas, tendrá que establecer procedimientos administrativos. Entre estos, se incluye la determinación de directivas para indicar qué personas de la organización pueden obtener una línea privada, la creación y administración de listas de personas y sus líneas de teléfono (porque los números de teléfono de líneas privadas no se almacenan en Active Directory), la posible creación de un directorio de teléfonos privados para ejecutivos, la preparación de formación para usuarios y otras tareas relacionadas.
  
> [!NOTE]
> La línea telefónica privada se almacena en Active Directory como un atributo msRTCSIP-PrivateLine en el objeto de usuario. De forma predeterminada los miembros del grupo Usuarios autenticados tiene acceso de lectura para este atributo. 
  
### <a name="assigning-telephone-numbers"></a>Asignación de números de teléfono

 Las cuentas de los nuevos usuarios que necesitan líneas telefónicas privadas se crean de la misma manera que las cuentas sin líneas telefónicas privadas, usando Skype Empresarial Server Panel de control o Skype Empresarial Server Shell de administración.
  
Use el cmdlet **Set-CsUser** en el Shell de administración de Skype Empresarial Server para asignar un número de teléfono a una línea telefónica privada para un usuario, por ejemplo, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212".**
  
Los números de teléfono de las líneas telefónicas privadas pueden tener entre 3 y 15 números de longitud y deben ir precedidos del prefijo "TEL:". Pueden tener cualquier código de área y de país, siempre que la organización disponga de llamada directa a la extensión para dicho código de área y de país/región. 
  
Para obtener más información acerca de los cmdlets y Skype Empresarial Server Shell de administración, consulte la Skype Empresarial Server del Shell de administración.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Líneas de teléfono privadas en implementaciones mezcladas

Las líneas telefónicas privadas solo deben configurarse para implementaciones de Skype Empresarial Server o Lync Server 2013. En una implementación en la que hay servidores que ejecutan versiones anteriores de Lync Server, cuando un usuario de la versión anterior intenta llamar a una línea de teléfono privada, el enrutamiento de la llamada falla porque el servidor no puede realizar una búsqueda de números inversos en una línea telefónica privada.
  

