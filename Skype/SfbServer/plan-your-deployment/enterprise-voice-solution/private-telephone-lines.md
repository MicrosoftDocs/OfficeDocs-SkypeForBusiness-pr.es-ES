---
title: Planificar líneas de teléfono privadas con Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planificación de líneas de teléfono privadas (secundarias) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813600"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planificar líneas de teléfono privadas con Skype Empresarial
 
Planificación de líneas de teléfono privadas (secundarias) en Skype Empresarial Server Telefonía IP empresarial.
  
Skype Empresarial Server le permite proporcionar a los usuarios una segunda línea de teléfono privada además de su línea de teléfono principal. Las líneas de teléfono privadas suelen asignarse a ejecutivos y a otros usuarios que desean un número de teléfono privado en el que se les pueda contactar directamente.
  
Las líneas de teléfono privadas solo se pueden configurar con el Shell de administración de Skype Empresarial Server. No puede configurar líneas de teléfono privadas con el Panel de control de Skype Empresarial Server. Las líneas de teléfono privadas solo deben configurarse en implementaciones de Skype Empresarial Server y no en implementaciones mixtas.
  
## <a name="characteristics-of-private-telephone-lines"></a>Características de las líneas de teléfono privadas

Aunque el concepto de una segunda línea de teléfono privada es fundamentalmente sencillo, es importante comprender las características de las líneas privadas y las formas en que son similares y diferentes de las líneas de teléfono principales de los usuarios.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Características generales de las líneas de teléfono privadas

- Un usuario solo puede tener una línea de teléfono privada.
    
- Los usuarios con una línea de teléfono privada solo disponen de un buzón de correo de voz y reciben notificaciones de llamadas perdidas en una única dirección de correo electrónico.
    
- Los usuarios con una línea de teléfono privada no disponen de una segunda dirección SIP y una segunda línea de teléfono privada no proporciona al usuario una segunda presencia en la red (como una segunda identidad de mensajería instantánea). 
    
- Las líneas de teléfono privadas solo están disponibles para implementaciones locales. No están disponibles con implementaciones hospedadas de Skype Empresarial Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Diferencias entre las líneas de teléfono privadas y las líneas de teléfono principales

- Los números de teléfono de las líneas de teléfono privadas no aparecen en los directorios de teléfonos ni en las listas de contactos que se obtienen de Servicios de dominio de Active Directory.
    
- Ninguna de las siguientes características están disponibles con una línea de teléfono privada: reenvío de llamadas, llamada de equipo, delegación, anillo de equipo, atención de llamadas grupales y aplicación grupo de respuesta.
    
- Las llamadas realizadas a una línea de teléfono privada suenan de una forma especial y la notificación del sistema para la llamada indica al usuario que la llamada entrante proviene de su línea privada.
    
- Las llamadas realizadas a la línea de teléfono privada siempre suenan. No siguen las reglas de "no molestar".
    
- Las líneas de teléfono privadas son solo entrantes y no pueden usarse para realizar llamadas salientes. Cuando un usuario con una línea de teléfono privada realiza una llamada, la llamada se origina en la línea de teléfono principal del usuario y no oculta el nombre del usuario ni el número de teléfono principal del usuario de la persona a la que se llama.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre las líneas de teléfono privadas y las líneas de teléfono principales

- Las llamadas no respondidas realizas a una línea de teléfono privada se enrutan a la misma bandeja de entrada de correo de voz de la línea telefónica principal (si el correo de voz está habilitado).
    
- El estacionamiento de llamadas y la atención de llamadas funcionan con líneas de teléfono privadas exactamente de la misma manera que con la línea de teléfono principal del usuario.
    
- Cuando se habilitan las llamadas simultáneas en la línea de teléfono principal de un usuario, también se habilita en la línea de teléfono privada.
    
- El número de teléfono de una línea de teléfono privada se registra en el registro detallado de llamadas de la misma manera que el número de teléfono de la línea de teléfono principal de un usuario, pero con una indicación de que se trata de un número de teléfono privado.
    
- Después de que un usuario responda a una llamada en una línea de teléfono privada, la llamada se trata igual que una llamada en la línea de teléfono principal del usuario. Por ejemplo, si un usuario que recibe una llamada en una línea de teléfono privada reenvía la llamada o invita a otras personas a una llamada de conferencia, el nombre del usuario aparece en Skype Empresarial y el número de teléfono de la línea de teléfono principal del usuario aparece en el identificador de llamada.
    
- Los usuarios pueden desviar una llamada de la línea de teléfono privada (redirigir la llamada a otro destino, como un teléfono móvil o un teléfono particular, antes de responder) de la misma forma que con una línea de teléfono principal. 
    
    > [!NOTE]
    > Cuando una llamada a una línea privada se enruta a un número de teléfono alternativo, el número de teléfono de la línea de teléfono privada se pone a disposición del número de teléfono alternativo y puede mostrarse en los registros de dicho número. 
  
    > [!NOTE]
    > Las llamadas desde una conferencia a la línea de teléfono privada no tendrán una indicación de  *línea*  privada en la notificación del sistema entrante.
  
## <a name="administering-private-telephone-lines"></a>Administración de líneas de teléfono privadas

Además de los aspectos técnicos de la creación y administración de líneas de teléfono privadas, tendrá que establecer procedimientos administrativos. Entre estos, se incluye la determinación de directivas para indicar qué personas de la organización pueden obtener una línea privada, la creación y administración de listas de personas y sus líneas de teléfono (porque los números de teléfono de líneas privadas no se almacenan en Active Directory), la posible creación de un directorio de teléfonos privados para ejecutivos, la preparación de formación para usuarios y otras tareas relacionadas.
  
> [!NOTE]
> La línea telefónica privada se almacena en Active Directory como un atributo msRTCSIP-PrivateLine en el objeto de usuario. De forma predeterminada los miembros del grupo Usuarios autenticados tiene acceso de lectura para este atributo. 
  
### <a name="assigning-telephone-numbers"></a>Asignación de números de teléfono

 Las cuentas para los nuevos usuarios que necesitan líneas de teléfono privadas se crean de la misma manera que las cuentas sin líneas de teléfono privadas, mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server.
  
Use el cmdlet **Set-CsUser** en el Shell de administración de Skype Empresarial Server para asignar un número de teléfono a una línea de teléfono privada para un usuario, por ejemplo, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.
  
Los números de teléfono de las líneas de teléfono privadas pueden tener entre 3 y 15 números de longitud y deben ir precedidos del prefijo "TEL:". Pueden tener cualquier código de área y de país, siempre que la organización disponga de llamada directa a la extensión para dicho código de área y de país/región. 
  
Para obtener más información sobre los cmdlets y el Shell de administración de Skype Empresarial Server, consulte la documentación del Shell de administración de Skype Empresarial Server.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Líneas de teléfono privadas en implementaciones mezcladas

Las líneas de teléfono privadas solo deben configurarse para las implementaciones de Skype Empresarial Server o Lync Server 2013. En una implementación en la que hay servidores que ejecutan versiones anteriores de Lync Server, cuando un usuario de una versión anterior intenta llamar a una línea de teléfono privada, se produce un error en el enrutamiento de la llamada porque el servidor no puede realizar una búsqueda inversa de números en una línea de teléfono privada.
  

