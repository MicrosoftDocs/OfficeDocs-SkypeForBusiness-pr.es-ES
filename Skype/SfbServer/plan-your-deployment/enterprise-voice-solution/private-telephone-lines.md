---
title: Planeación de líneas de teléfono privadas con Skype para la empresa
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planeación de las líneas de teléfono (secundario) privada de Skype para Business Server Enterprise Voice.
ms.openlocfilehash: f8bc6b19ab28971de87cdf985373b8b70d67a36c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884138"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planeación de líneas de teléfono privadas con Skype para la empresa
 
Planeación de las líneas de teléfono (secundario) privada de Skype para Business Server Enterprise Voice.
  
Skype para Business Server le permite conceder a los usuarios una línea de teléfono en segundo lugar, privada además de su línea de teléfono principal. Las líneas de teléfono privadas suelen asignarse a ejecutivos y a otros usuarios que desean un número de teléfono privado en el que se les pueda contactar directamente.
  
Líneas de teléfono privadas sólo pueden configurarse con el Skype para Shell de administración de servidor empresarial. No se puede configurar líneas de teléfono privadas con el Skype para el Panel de Control de servidor empresarial. Líneas de teléfono privadas deben configurarse únicamente en las implementaciones de Skype para Business Server y no en implementaciones mixtas.
  
## <a name="characteristics-of-private-telephone-lines"></a>Características de las líneas de teléfono privadas

Aunque el concepto de una línea de teléfono en segundo lugar, privada es fundamentalmente simple, es importante comprender las características de líneas privadas y las formas en que son similares a y diferente de las líneas de teléfono principal de los usuarios.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Características generales de las líneas de teléfono privadas

- Un usuario solo puede tener una línea de teléfono privada.
    
- Los usuarios con una línea de teléfono privada solo disponen de un buzón de correo de voz y reciben notificaciones de llamadas perdidas en una única dirección de correo electrónico.
    
- Los usuarios con una línea de teléfono privada no disponen de una segunda dirección SIP y una segunda línea de teléfono privada no proporciona al usuario una segunda presencia en la red (como una segunda identidad de mensajería instantánea). 
    
- Las líneas de teléfono privadas solo están disponibles para implementaciones locales. No están disponibles con implementaciones hospedadas de Skype para Business Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Diferencias entre las líneas de teléfono privadas y las líneas de teléfono principales

- Los números de teléfono de las líneas de teléfono privadas no aparecen en los directorios de teléfonos ni en las listas de contactos que se obtienen de Servicios de dominio de Active Directory.
    
- Ninguna de las características siguientes está disponible con una línea de teléfono privada: desvío de llamadas, llamada de equipo, delegación, respuesta de llamadas en grupo y la aplicación Grupo de respuesta.
    
- Las llamadas realizadas a una línea de teléfono privada suenan de una forma especial y la notificación del sistema para la llamada indica al usuario que la llamada entrante proviene de su línea privada.
    
- Las llamadas realizadas a la línea de teléfono privada siempre suenan. No siguen las reglas de "no molestar".
    
- Las líneas de teléfono privadas son solo entrantes y no pueden usarse para realizar llamadas salientes. Cuando un usuario con una línea de teléfono privada realiza una llamada, la llamada se origina desde la línea de teléfono principal del usuario y no oculta el nombre del usuario o número de teléfono principal del usuario de la persona que llama.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre las líneas de teléfono privadas y las líneas de teléfono principales

- Las llamadas no respondidas realizas a una línea de teléfono privada se redirigen a la misma bandeja de entrada de correo de voz de la línea telefónica principal (si el correo de voz está habilitado).
    
- Estacionamiento y atención de llamadas funcionan con líneas de teléfono privadas exactamente la misma manera como lo hacen con la línea de teléfono principal del usuario.
    
- Cuando las llamadas simultáneas está habilitada en la línea de teléfono principal de un usuario, también está habilitada en la línea de teléfono privada.
    
- El número de teléfono para una línea de teléfono privada se registra en el registro de detalles de llamadas en la misma manera que el número de teléfono de la línea de teléfono principal de un usuario, pero con una indicación de que es un número de teléfono privado.
    
- Después de que un usuario respuestas que una llamada en una línea de teléfono privadas, la llamada es el mismo tratan como una llamada en la línea de teléfono principal del usuario. Por ejemplo, si un usuario que recibe una llamada en una línea de teléfono privada reenvía la llamada o invita a otras personas a una llamada de conferencia, el nombre del usuario aparece en Skype para la empresa y el número de teléfono de la línea de teléfono principal del usuario aparece en el autor de la llamada identificador.
    
- Los usuarios pueden desviar una llamada de la línea de teléfono privada (redirigir la llamada a otro destino, como un teléfono móvil o un teléfono particular, antes de responder) de la misma forma que con una línea de teléfono principal. 
    
    > [!NOTE]
    > Cuando una llamada a una línea privada se redirige a un número de teléfono alternativo, el número de teléfono de la línea de teléfono privada se pone a disposición del número de teléfono alternativo y puede mostrarse en los registros de dicho número. 
  
    > [!NOTE]
    > Llamadas desde una conferencia a la línea de teléfono privada no tendrán una indicación *línea a privada* en la notificación entrante del sistema.
  
## <a name="administering-private-telephone-lines"></a>Administración de líneas de teléfono privadas

Además de los aspectos técnicos de la creación y administración de líneas de teléfono privadas, tendrás que establecer procedimientos administrativos. Entre estos, se incluye la determinación de directivas para indicar qué personas de la organización pueden obtener una línea privada, la creación y administración de listas de personas y sus líneas de teléfono, la posible creación de un directorio de teléfonos privados para ejecutivos, la preparación de formación para usuarios y otras tareas relacionadas.
  
> [!NOTE]
> La línea telefónica privada se almacena en Active Directory como un atributo msRTCSIP-PrivateLine en el objeto de usuario. De forma predeterminada, los miembros del grupo Usuarios autenticados tienen acceso de lectura para este atributo. 
  
### <a name="assigning-telephone-numbers"></a>Asignar números de teléfono

 Las cuentas para los nuevos usuarios que necesitan líneas de teléfono privadas se crean de la misma manera que las cuentas sin líneas de teléfono privadas, mediante Skype para el Panel de Control de servidor empresarial o Skype para Shell de administración de servidor empresarial.
  
Use el cmdlet **Set-CsUser** en el Skype para Shell de administración de servidor empresarial para asignar un número de teléfono a una línea telefónica privada de un usuario, por ejemplo, **Set-CsUser-Identity "sip:joe@contoso.com" - PrivateLine "Tel: + 14255551212"**.
  
Números de teléfono de líneas de teléfono privadas puede estar comprendido entre 3 y 15 números de longitud y deben ir precedidos con el "TEL:" prefijo. Pueden tener cualquier código de área y de país, siempre que la organización disponga de llamada directa a la extensión para dicho código de área y de país o región. 
  
Para obtener información detallada acerca de los cmdlets y Skype para Shell de administración de servidor empresarial, vea el Skype para la documentación del Shell de administración de servidor empresarial.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Líneas de teléfono privadas en implementaciones combinadas

Líneas de teléfono privadas deben configurarse sólo para las implementaciones de Skype para Business Server o Lync Server 2013. En una implementación en la que hay servidores que ejecutan versiones anteriores de Lync Server, cuando un usuario de la versión anterior intenta llamar a una línea telefónica privada, el enrutamiento de la llamada se produce un error debido a que el servidor no puede realizar una búsqueda inversa de números en una línea de teléfono privada.
  

