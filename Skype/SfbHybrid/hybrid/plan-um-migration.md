---
title: Plan para la migración de Skype Empresarial Server y Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: En este tema se describe lo que debe tener en cuenta al decidir migrar las implementaciones de Skype Empresarial Server o Exchange Server existentes a la versión más reciente o a Skype Empresarial Online o Exchange Online.
ms.openlocfilehash: ace5151a9a1a910b12b7cba36340bd00f2e96874
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486995"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Plan para la migración de Skype Empresarial Server y Exchange Server

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este tema se describe lo que debe tener en cuenta al decidir migrar las implementaciones de Skype Empresarial Server o Exchange Server existentes a Exchange Online. Lo que puede migrar y cuándo depende en gran medida de lo que ya tiene configurado en su organización.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Cambios de características en Exchange 2019 y Skype Empresarial Server 2019

Con Exchange 2019 y Skype Empresarial Server 2019, estamos realizando algunos cambios en las características que se admiten.

### <a name="unified-messaging-support-in-exchange-2019"></a>Compatibilidad con mensajería unificada en Exchange 2019

La mensajería unificada (UM) ha quedado en desuso en Exchange 2019. Esto significa que Exchange 2019 ya no ofrece las siguientes características:

- Correo de voz
- Operador automático

Si ha implementado el rol de mensajería unificada en Exchange 2013 o el servicio de mensajería unificada en Exchange 2016 y desea actualizar a Exchange 2019, deberá migrar el correo de voz al servicio de Correo de voz en la nube de Microsoft en Microsoft 365 o Office 365. Si desea migrar el correo de voz a Correo de voz en la nube, eche un vistazo a la sección [Exchange 2013/Exchange 2016 y Skype Empresarial 2015 a Exchange 2019 y Skype Empresarial 2019 a](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) continuación.
> [!IMPORTANT]
> Si los usuarios de los servidores de Exchange 2013 o Exchange 2016 tienen buzones habilitados para mensajería unificada, no los mueva a Exchange 2019 antes de actualizar los servidores de Skype Empresarial a Skype Empresarial Server 2019 y mover los usuarios a ellos para evitar una interrupción de la mensajería de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Compatibilidad con PBX en Exchange 2019 y Skype Empresarial Server 2019

Correo de voz en la nube no proporciona funcionalidad de mensajería de voz a las Centrales de sucursal privadas (PBX). Si usa Exchange Server mensajería unificada para PBX y quiere actualizar a Exchange Server 2019, deberá adoptar una de las tres opciones que se enumeran en la entrada de blog [Nueva fecha para la interrupción de la compatibilidad con controladores de borde de sesión en Exchange Online mensajería unificada](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) en el [blog del equipo de Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online compatibilidad con mensajería unificada en Skype Empresarial Server 2019

Con Skype Empresarial Server 2019, pasaremos de Exchange Online mensajería unificada a Correo de voz en la nube. Cuando un usuario se mueve a un servidor de Skype Empresarial 2019, comenzará automáticamente a usar Correo de voz en la nube cuando esté configurado para el correo de voz hospedado. Si actualmente usa Exchange Online mensajería unificada, no es necesario hacer nada más que mover un usuario a Skype Empresarial Server 2019 para empezar a usar Correo de voz en la nube. Sin embargo, hay algunos cambios en la funcionalidad que debe tener en cuenta:

- El operador automático de la organización es el reemplazo del operador automático en Exchange Online mensajería unificada.
- La configuración del correo de voz del usuario en Outlook en la Web no se aplica a Correo de voz en la nube.

## <a name="on-premises-um-migration-scenarios"></a>Escenarios de migración de mensajería unificada local

Se admiten los siguientes escenarios que le permitirán migrar usuarios a Exchange 2019 y a Correo de voz en la nube.

- Exchange 2013/Exchange 2016 y Skype Empresarial Server 2015 a Exchange 2019 y Skype Empresarial Server 2019
- Skype Empresarial Server 2015 a Skype Empresarial Server 2019 con Exchange 2013/Exchange 2016

Los escenarios siguientes requieren que no existan configuraciones de PBX o SBC como parte de la implementación actual y se supone que tiene la mensajería unificada configurada en los servidores de Exchange locales. Cada una de estas soluciones también supone que ha decidido configurar una implementación híbrida entre los servidores de Skype Empresarial locales y Microsoft 365 o Office 365. Para obtener más información sobre Skype Empresarial implementaciones híbridas, consulte [Planeamiento de la conectividad híbrida](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 y Skype Empresarial 2015 a Exchange 2019 y Skype Empresarial 2019

En este escenario, quiere migrar los servidores existentes de Exchange 2013, Exchange 2016 y Skype Empresarial 2015 a Exchange 2019 y Skype Empresarial 2019.

Como se mencionó anteriormente en este tema, Exchange 2019 ya no incluye el servicio de mensajería unificada. Esto significa que, para los buzones que quiera mover a Exchange 2019, debe usar Correo de voz en la nube para reemplazar la funcionalidad proporcionada por el servicio de mensajería unificada. Al configurar Skype Empresarial Server 2019 y una implementación híbrida entre ella y Microsoft 365 o Office 365, Correo de voz en la nube reemplaza estos servicios de correo de voz de mensajería unificada de Exchange.

El orden en el que mueve los usuarios a Exchange 2019 y Skype Empresarial Server 2019 es fundamental para garantizar que la funcionalidad del correo de voz permanezca disponible para todos los usuarios. El lugar en el que se procesa el correo de voz también viene determinado por dónde se encuentran los buzones y los usuarios de Exchange y Skype Empresarial. Eche un vistazo a la tabla siguiente para ver qué combinaciones de Exchange y Skype Empresarial Server se admiten y dónde se procesa el correo de voz.

| Buzón ubicado en:            | Usuario ubicado en Skype Empresarial Server 2015 | Usuario ubicado en Skype Empresarial Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | UM de Exchange                             | UM de Exchange                              |
| Exchange 2019                  | No compatible                           | Correo de voz en la nube                          |

Antes de iniciar la migración a Skype Empresarial Server 2019 y Exchange 2019, tenga en cuenta lo siguiente:

- Debe configurar al menos un servidor Skype Empresarial 2019 **y** mover usuarios a ese servidor antes de mover sus buzones a Exchange 2019. Si no lo hace, esos buzones no podrán recibir mensajes de correo de voz.
- Las llamadas enviadas al correo de voz se transferirán a Correo de voz en la nube donde se grabarán. Una vez finalizada la llamada, el mensaje de correo de voz se enviará al buzón del destinatario en el servidor local de Exchange 2019. Debe tener en cuenta este tráfico de voz al determinar si la conectividad a Internet es suficiente para admitir Correo de voz en la nube.

Estos son los pasos de alto nivel para completar esta migración.

1. Instale y configure Skype Empresarial Server 2019 en un nuevo servidor.
2. Actualice la configuración de implementación híbrida para incluir el nuevo servidor de Skype Empresarial 2019.
3. Instale y configure Exchange Server 2019 en un nuevo servidor.
4. Mueva los usuarios del servidor de Skype Empresarial 2015 al servidor de Skype Empresarial 2019.
5. Establezca la directiva de correo de voz hospedado para cada usuario que se haya movido a Skype Empresarial Server 2019 para usar Correo de voz en la nube.
6. Mueva los buzones de correo del servidor de Exchange 2013 o Exchange 2016 al servidor de Exchange 2019.
7. Retire los servidores Skype Empresarial 2015 después de que el último usuario se haya quitado de ellos.
8. Retire los servidores de Exchange 2013 o Exchange 2016 después de que el último buzón se haya quitado de ellos.


### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype Empresarial Server 2015 a Skype Empresarial Server 2019 con Exchange 2013/Exchange 2016

En este escenario, quiere migrar el servidor de Skype Empresarial 2015 existente a Skype Empresarial Server 2019, pero permanecer en Exchange 2013 o Exchange 2016.

Cuando Skype Empresarial Server 2015 y Skype Empresarial Server 2019 coexisten en la misma organización, funcionan sin problemas con la mensajería unificada de Exchange y Correo de voz en la nube para asegurarse de que el correo de voz se entrega correctamente a los buzones de Exchange. Si la mensajería unificada de Exchange o Correo de voz en la nube procesa el correo de voz depende de si el usuario se encuentra en Skype Empresarial Server 2015 o Skype Empresarial Server 2019:

- Si un usuario se encuentra en Skype Empresarial Server 2015, la mensajería unificada de Exchange procesará el mensaje de correo de voz.
- Si un usuario se encuentra en Skype Empresarial Server 2019, Correo de voz en la nube procesará el mensaje de correo de voz.

Independientemente de si la mensajería unificada de Exchange o Correo de voz en la nube procesa el mensaje de correo de voz, el mensaje se almacenará en el buzón de Exchange del usuario.

Antes de iniciar la migración a Skype Empresarial Server 2019, tenga en cuenta lo siguiente:

- Las llamadas enviadas al correo de voz se transferirán a Correo de voz en la nube donde se grabarán. Una vez finalizada la llamada, el mensaje de correo de voz se enviará al buzón del destinatario en el servidor exchange local. Debe tener en cuenta este tráfico de voz al determinar si la conectividad a Internet es suficiente para admitir Correo de voz en la nube.

Estos son los pasos de alto nivel para completar esta migración.

1. Instale y configure Skype Empresarial Server 2019 en un nuevo servidor.
2. Actualice la configuración de implementación híbrida para incluir el nuevo servidor de Skype Empresarial 2019.
3. Mueva los usuarios del servidor de Skype Empresarial 2015 al servidor de Skype Empresarial 2019.
4. Establezca la directiva de correo de voz hospedado para cada usuario que se haya movido a Skype Empresarial Server 2019 para usar Correo de voz en la nube.
5. Retire los servidores Skype Empresarial 2015 después de que el último usuario se haya quitado de ellos.

