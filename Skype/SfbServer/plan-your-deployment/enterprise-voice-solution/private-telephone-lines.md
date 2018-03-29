---
title: Planificar líneas telefónicas privadas con Skype Empresarial 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Diseño para líneas de teléfono (secundario) privada de Skype de Telefonía IP empresarial de Business Server.
ms.openlocfilehash: ae1d992890d2faa1db9de097a519d363b9e1c228
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business-2015"></a>Planificar líneas telefónicas privadas con Skype Empresarial 2015
 
Diseño para líneas de teléfono (secundario) privada de Skype de Telefonía IP empresarial de Business Server.
  
Skype para Business Server le permite proporcionar a los usuarios una línea de teléfono privado, segundo además de su línea de teléfono principal. Las líneas de teléfono privadas suelen asignarse a ejecutivos y a otros usuarios que desean un número de teléfono privado en el que se les pueda contactar directamente.
  
Líneas de teléfono privado sólo pueden configurarse con el Skype para el Shell de administración de servidor de empresa. No puede configurar las líneas telefónicas privadas con el Skype para el Panel de Control de servidor empresarial. Líneas telefónicas privadas deben configurarse sólo en implementaciones de Skype para Business Server y no en distribuciones mixtas.
  
## <a name="characteristics-of-private-telephone-lines"></a>Características de las líneas de teléfono privadas

Aunque el concepto de una línea telefónica privada, segundo es fundamentalmente simple, es importante entender las características de líneas privadas y las maneras en que son similares a y diferente de las líneas de teléfono principal de los usuarios.
  
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
    
- Las líneas de teléfono privadas son solo entrantes y no pueden usarse para realizar llamadas salientes. Cuando un usuario con una línea telefónica privada hace una llamada, la llamada se origina en la línea de teléfono principal del usuario y no oculta el nombre del usuario o número de teléfono principal del usuario de la persona que llama.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre las líneas de teléfono privadas y las líneas de teléfono principales

- Las llamadas no respondidas realizas a una línea de teléfono privada se redirigen a la misma bandeja de entrada de correo de voz de la línea telefónica principal (si el correo de voz está habilitado).
    
- Llamada en espera y llame recogida funcionan con líneas telefónicas privadas de exactamente de la misma manera como lo hacen con la línea de teléfono principal del usuario.
    
- Cuando está habilitada la llamadas simultáneas en la línea de teléfono principal de un usuario, también está habilitada en la línea de teléfono privado.
    
- El número de teléfono de una línea telefónica privada se graba en el registro de detalle de llamada de la misma manera que el número de teléfono para la línea de teléfono principal de un usuario, pero con una indicación de que es un número de teléfono privado.
    
- Después de que un usuario respuestas que es una llamada en una línea telefónica privada, la llamada tratan igual que una llamada en la línea de teléfono principal del usuario. Por ejemplo, si un usuario que recibe una llamada en una línea telefónica privada reenvía la llamada o invita a otros a una llamada de conferencia, el nombre del usuario aparece en Skype para el negocio y el número de teléfono para la línea de teléfono principal del usuario aparece en el llamador Id.
    
- Los usuarios pueden desviar una llamada de la línea de teléfono privada (redirigir la llamada a otro destino, como un teléfono móvil o un teléfono particular, antes de responder) de la misma forma que con una línea de teléfono principal. 
    
    > [!NOTE]
    > Cuando una llamada a una línea privada se redirige a un número de teléfono alternativo, el número de teléfono de la línea de teléfono privada se pone a disposición del número de teléfono alternativo y puede mostrarse en los registros de dicho número. 
  
    > [!NOTE]
    > Llamadas desde una conferencia a la línea telefónica privada no tendrá una indicación de *línea a privada* en el sistema de notificación entrante.
  
## <a name="administering-private-telephone-lines"></a>Administración de líneas de teléfono privadas

Además de los aspectos técnicos de la creación y administración de líneas de teléfono privadas, tendrás que establecer procedimientos administrativos. Entre estos, se incluye la determinación de directivas para indicar qué personas de la organización pueden obtener una línea privada, la creación y administración de listas de personas y sus líneas de teléfono, la posible creación de un directorio de teléfonos privados para ejecutivos, la preparación de formación para usuarios y otras tareas relacionadas.
  
> [!NOTE]
> La línea telefónica privada se almacena en Active Directory como un atributo msRTCSIP-PrivateLine en el objeto de usuario. De forma predeterminada, los miembros del grupo Usuarios autenticados tienen acceso de lectura para este atributo. 
  
### <a name="assigning-telephone-numbers"></a>Asignar números de teléfono

 Cuentas para los nuevos usuarios que necesitan líneas telefónicas privadas se crean de la misma manera como cuentas sin líneas de teléfono privado, con Skype para Business Server Control Panel o Skype para el Shell de administración de servidor empresarial.
  
Utilice el cmdlet **Set-CsUser** en el Skype para negocios de Shell de administración de servidor para asignar un número de teléfono a una línea telefónica privada de un usuario, por ejemplo, **conjunto CsUser-Identity "sip:joe@contoso.com" - PrivateLine "Tel: + 14255551212"**.
  
Números de teléfono de líneas telefónicas privadas puede estar comprendido entre 3 y 15 números de longitud y deben ir precedidos por el "TEL:" prefijo. Pueden tener cualquier código de área y de país, siempre que la organización disponga de llamada directa a la extensión para dicho código de área y de país o región. 
  
Para obtener más información acerca de los cmdlets y Skype para negocios de Shell de administración de servidor, vea el Skype para la documentación del Shell de administración de servidor empresarial.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Líneas de teléfono privadas en implementaciones combinadas

Líneas telefónicas privadas deben configurarse sólo para las implementaciones de Skype para Business Server o Lync Server 2013. En una implementación donde hay servidores que ejecutan versiones anteriores de Lync Server, cuando un usuario de la versión anterior intenta llamar a una línea telefónica privada, enrutamiento de la llamada produce un error porque el servidor no puede realizar una búsqueda de número inversa en una línea de teléfono privado.
  

