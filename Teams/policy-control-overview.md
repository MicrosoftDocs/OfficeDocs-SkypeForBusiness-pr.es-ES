---
title: Introducción al control de directivas para Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Información general sobre los controles de directivas para Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3665f386f43d8e9b8c49a024663265c25ae96214
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136109"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Introducción al control de directivas para Microsoft Teams

Microsoft se compromete a proporcionarle la información y los controles que necesita para decidir cómo se recopilan y usan sus datos cuando usa Microsoft Teams, que forma parte de Microsoft 365.

Este artículo ha sido diseñado para proporcionarle información acerca de los controles de privacidad de las siguientes áreas:

- **Datos de diagnóstico** que son recopilados y enviados a Microsoft acerca del software de Teams y Office que se usa en los ordenadores en los que se ejecuta Windows en su organización.
- **Experiencias conectadas** que utilizan la funcionalidad en la nube para proporcionar funciones mejoradas de Teams y Office para usted y sus usuarios.

Como parte de estos cambios, puede contar con una configuración de directivas y elementos de la interfaz de usuario nuevos y actualizados

> [!IMPORTANT]
> Para obtener más información, consulte la [introducción al control de directivas](https://docs.microsoft.com/deployoffice/privacy/overview-privacy-controls), contenido para M365.

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>Datos de diagnóstico enviados de Aplicaciones de Microsoft 365 para empresas a Microsoft.

Los datos de diagnóstico se usan para:

- Mantener Teams seguro y actualizado.
- Detectar, diagnosticar y solucionar problemas.
- Realizar mejoras al producto.

Un ejemplo de algunos de los datos recopilados son:

- Idioma de la aplicación
- Tipo de usuario
- Versión de compilación del sistema operativo

## <a name="clients-that-adhere-to-diagnostic-controls"></a>Clientes que se adhieren a los controles de diagnóstico

Los siguientes clientes se adhieren a los controles de diagnóstico y enviarán los datos:

- iOS
- Android
- Escritorio (solo el componente que usa la API de Win32)

Para información acerca de los diagnósticos necesarios de datos móviles, consulte [datos de diagnóstico del control de directivas para móviles](policy-control-diagnostic-data-mobile.md).

Para información acerca de los diagnósticos necesarios del escritorio, consulte [datos de diagnóstico del control de directivas para escritorio](policy-control-diagnostic-data-desktop.md).

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Datos de diagnóstico enviados desde la aplicación Teams a Microsoft

Estos datos de diagnósticos se recopilan y envían a Microsoft sobre el software de cliente de Teams que usan los equipos que ejecutan Windows en su organización.

Existen tres niveles de datos de diagnóstico para el software de Teams entre los que puede elegir:

- **Necesarios** Los datos mínimos necesarios para mantener Office protegido, actualizado y con el rendimiento esperado en el dispositivo que se instala.
- **Opcionales** Otros datos que nos ayudan a mejorar el producto y proporcionan información mejorada para ayudarnos a detectar, diagnosticar y solucionar problemas.
- **Ninguno** No se recopila ni envía ningún dato de diagnóstico sobre el software de Teams que se ejecuta en el dispositivo del usuario. Esta opción, sin embargo, limita considerablemente nuestra capacidad de detectar, diagnosticar y solucionar problemas que puedan encontrar los usuarios al usar Teams.

Los datos de diagnósticos necesarios podrían incluir, por ejemplo, información sobre la versión del cliente de Teams instalada en el dispositivo o información que indica que la aplicación Teams se bloquea al intentar unirse a una reunión. Los datos de diagnósticos opcionales pueden incluir información sobre el tiempo necesario para iniciar una llamada, lo que podría indicar un problema con la conectividad o el rendimiento de red.

Si elige enviarnos sus datos de diagnóstico opcionales, también se incluyen los datos de diagnósticos necesarios.

Como administrador de su organización, podrá usar una configuración de directiva para elegir qué nivel de datos de diagnóstico se envían. Los datos de diagnóstico opcionales se enviarán a Microsoft a menos que cambie la configuración. Proporcionar datos de diagnóstico opcionales facilita al equipo de ingeniería de Office de Microsoft la detección, diagnostico y solución de los problemas para reducir el impacto en su organización.

Los usuarios no podrán cambiar el nivel de datos de diagnóstico para sus dispositivos si han iniciado sesión en Teams con sus credenciales de la organización (su cuenta profesional o educativa).

Estos datos de diagnóstico no incluyen los nombres de los usuarios, sus direcciones de correo electrónico o el contenido de sus archivos de Office. El sistema crea un identificador único que asocia a los datos de diagnóstico de los usuarios. Cuando recibimos datos de diagnóstico en los que se muestra que la aplicación Teams se ha bloqueado 100 veces, este identificador único nos permite determinar si se trata de un único usuario que ha tenido el problema 100 veces o si se trata de 100 usuarios diferentes que lo han tenido una vez. No usamos este identificador único para identificar a un usuario específico.

## <a name="required-service-data-for-connected-experiences"></a>Datos de servicio necesarios para experiencias conectadas

Los datos de servicio requeridos son aquellos que nos permiten ofrecer estas experiencias conectadas basadas en la nube, ayudan a que estas experiencias sean seguras y tengan el funcionamiento esperado. Los datos requeridos del servicio se componen de tres tipos de información.

- **Contenido del cliente**, que es el contenido que se crea al usar Office, como el texto escrito en un documento de Word.
- **Datos funcionales**, que incluyen la información que necesita una experiencia conectada para realizar la tarea, como la información de configuración de la aplicación.
- **Datos de diagnóstico de servicio**, que son los datos necesarios para proteger el servicio y mantenerlo actualizado y funcionando según lo esperado. Dado que estos datos están estrictamente relacionados con la experiencia conectada, son independientes de los niveles de datos de diagnóstico necesarios u opcionales.

Puede optar por no ofrecer esta funcionalidad a los usuarios, en cuyo caso esta información no se proporcionará a Microsoft para admitir la funcionalidad de las experiencias conectadas. Puede obtener más información acerca de los [datos de servicio necesarios](https://docs.microsoft.com/deployoffice/privacy/required-service-data).

## <a name="essential-services-for-microsoft-teams"></a>Servicios esenciales para Microsoft Teams

También existe un conjunto de servicios que son esenciales para el funcionamiento de Aplicaciones de Microsoft 365 para empresas y no se pueden deshabilitar. Por ejemplo, el servicio de licencias que confirma que tiene una licencia correcta de uso de Aplicaciones de Microsoft 365 para empresas. Los datos de servicio requeridos sobre estos servicios se recopilan y envían a Microsoft, independientemente de cualquier otra configuración de directiva que haya establecido.

Para obtener más información, consulte [Servicios esenciales de Office](https://docs.microsoft.com/deployoffice/privacy/essential-services).
