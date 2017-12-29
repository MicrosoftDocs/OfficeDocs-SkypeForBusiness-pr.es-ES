---
title: Interoperabilidad entre Microsoft Teams y Skype Empresarial
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Comprenda la interoperabilidad entre Microsoft Teams y Skype Empresarial, y cómo esta afecta a las experiencias de chat y llamada."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a6593d6e2bc7302817a87c418da4bacb70f03b42
ms.sourcegitcommit: 334fee0485e16a6485055eff586203cc30e6fdc9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2017
---
<a name="microsoft-teams-and-skype-for-business-interoperability"></a>Interoperabilidad entre Microsoft Teams y Skype Empresarial
=======================================================

Si su organización usa Skype Empresarial actualmente y pretende empezar a usar Microsoft Teams, es importante que comprenda cómo configurar las dos aplicaciones para garantizar la interoperabilidad.

> [!IMPORTANT]
> Este documento se ofrece para realizar una evaluación temprana de la compatibilidad de Planes de llamada en Microsoft Teams. Se prevé el cambio de los detalles de la directiva de interoperabilidad de Microsoft Teams en el futuro.

La interoperabilidad permite a los usuarios de Skype Empresarial y Microsoft Teams chatear y realizar llamadas entre sí, con lo que se logra una comunicación fluida en toda la organización. Para ayudar a los profesionales de TI a administrar la adopción de Microsoft Teams, hemos añadido una nueva directiva de interoperabilidad de Microsoft Teams que se administra a través de una sesión remota de Windows PowerShell en Skype Empresarial mediante cmdlets [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype). Use esta directiva para configurar Microsoft Teams del modo que necesite para su organización.


> [!TIP]
> Para buscar los cmdlets de PowerShell que necesita para habilitar la interoperabilidad, escriba "CsTeamsInteropPolicy" en el cuadro **Filtrar** en la [documentación sobre los cmdlets de PowerShell para Skype Empresarial](https://docs.microsoft.com/powershell/module/skype).

La directiva de interoperabilidad de Microsoft Teams permite a los profesionales de TI designar la aplicación preferida de un usuario para recibir mensajes de chat y llamadas. Se puede configurar para mantener aisladas las comunicaciones en Microsoft Teams y Skype Empresarial, o para permitir que los usuarios se comuniquen superando los límites de las aplicaciones.

La directiva de interoperabilidad de Microsoft Teams se puede definir por inquilino o por usuario, e incluso se puede configurar para que los usuarios puedan elegir qué aplicación quieren usar para recibir mensajes de chat y llamadas.

Esta flexibilidad integrada se proporciona para ayudar a su organización a probar y evaluar Microsoft Teams, y realizar la migración a esta aplicación al ritmo y del modo que mejor le convenga.

> [!NOTE]
> La interoperabilidad entre Microsoft Teams y Skype Empresarial es posible entre usuarios que trabajan totalmente en línea (Skype Empresarial Online y Microsoft Teams) y usuarios en una implementación local de Skype Empresarial con una topología de implementación mixta (híbrida).

## <a name="what-interoperability-means"></a>Qué significa interoperabilidad
Interoperabilidad es la capacidad de los usuarios de Microsoft Teams y Skype Empresarial de chatear (MI) y realizar llamadas entre sí tanto desde Microsoft Teams como desde Skype Empresarial.

Cuando las organizaciones comienzan la transición de Skype Empresarial a Microsoft Teams, la previsión es que habrá una combinación de usuarios utilizando clientes diferentes en la organización.

Para garantizar una productividad ininterrumpida, Microsoft Teams permite que los usuarios se comuniquen entre sí sin importar qué aplicación utilicen (Microsoft Teams o Skype Empresarial).

Las experiencias de interoperabilidad admitidas son, entre otras:
- Los usuarios de Skype Empresarial que no usan Microsoft Teams pueden chatear con usuarios de Microsoft Teams y viceversa.<p>
![Experiencia de chat desde Microsoft Teams con interoperabilidad](media/Interop_chat_experience_from_Teams.png)<br>
- Los usuarios de Skype Empresarial pueden hablar con los usuarios de Microsoft Teams mediante llamadas por voz y vídeo, y viceversa. Las opciones de llamada avanzadas, como la transferencia y el desvío de llamadas seguirán funcionando, incluso en las llamadas con interoperabilidad.<p>
![Experiencia de llamada desde Microsoft Teams con interoperabilidad](media/Interop_calling_experience_from_Teams.png)<br>

> [!NOTE]
> Desde el punto de vista de un usuario de Skype Empresarial, los chats y las llamadas a/desde Microsoft Teams se mostrarán como chats y llamadas básicos de Skype Empresarial. Consulte la sección [Limitaciones de las experiencias de interoperabilidad](#interop-experiences-limitations) para obtener más detalles.

> [!IMPORTANT]
> La presencia unificada entre Microsoft Teams y Skype Empresarial no es compatible actualmente, lo que significa que Microsoft Teams y Skype Empresarial mostrarán sus estados de presencia independientes. Para descubrir cuándo estará disponible la compatibilidad con la presencia unificada, consulte [De Skype Empresarial a Microsoft Teams: mapa de ruta de las opciones](https://aka.ms/skype2teamsroadmap).

## <a name="interop-requirements"></a>Requisitos para la interoperabilidad
Para que se habiliten las funcionalidades de interoperabilidad, los usuarios deben cumplir los siguientes criterios:
- Los usuarios deben estar habilitados (o tener licencia) para Microsoft Teams
- Los usuarios deben estar habilitados (o tener licencia) para Skype Empresarial Online
    - Esto es aplicable a los usuarios que planeen usar Microsoft Teams solo o Microsoft Teams como su aplicación principal de chat y llamadas.
- En una implementación de Skype Empresarial híbrida:
    - Los usuarios que se encuentren en una implementación local de Skype Empresarial (o una versión de Lync Server admitida actualmente para la implementación de Skype Empresarial Híbrido) disfrutan de interoperabilidad con usuarios en la nube que usen Microsoft Teams.
    - Los usuarios en la nube que planeen usar Microsoft Teams como su aplicación de chat y llamadas principal deben estar habilitados (o tener licencia) para Skype Empresarial Online.

## <a name="supported-topologies-for-interop"></a>Topologías admitidas para la interoperabilidad
La interoperabilidad entre Microsoft Teams y Skype Empresarial admite las siguientes topologías de implementación de Skype Empresarial:
- Solo Skype Empresarial Online
- Skype Empresarial Híbrido (implementación mixta de Skype Empresarial Online y Skype Empresarial local)

### <a name="skype-for-business-online-only-topology"></a>Topología de solo Skype Empresarial Online
Las organizaciones con una implementación de solo Skype Empresarial Online pueden beneficiarse de la compatibilidad de la interoperabilidad para chat y llamadas entre usuarios de Skype Empresarial Online y de Microsoft Teams.

En esta topología, será necesario habilitar a los usuarios configurados con Microsoft Teams como su aplicación principal de chat y llamadas también para Skype Empresarial Online para que funcione la interoperabilidad.

![Interoperabilidad en una topología de implementación de solo Skype Empresarial Online](media/Interop_SkypeforBusinessOnlineOnly_topology.png)

### <a name="skype-for-business-hybrid-deployment-topology"></a>Topología de implementación de Skype Empresarial Híbrido
Las organizaciones con una implementación compuesta por una implementación mixta de Skype Empresarial Online y Skype Empresarial Server (local) en una topología de implementación híbrida se pueden beneficiar de la compatibilidad de la interoperabilidad para chat y llamadas entre usuarios de Skype Empresarial (alojados en línea o localmente) y de Microsoft Teams.

Al igual que en una topología de implementación de solo Skype Empresarial Online, será necesario habilitar a los usuarios configurados con Microsoft Teams como su aplicación principal de chat y llamadas también para Skype Empresarial Online y local para que funcione la interoperabilidad.

![Interoperabilidad en una topología de implementación de Skype Empresarial Híbrido](media/Interop_SkypeforBusinessHybrid_topology.png)

> [!IMPORTANT]
> La compatibilidad de la interoperabilidad para Skype Empresarial Híbrido no incluye las funcionalidades de voz híbrida que se proporcionan a través de CCE (Cloud Connector Edition) o la conectividad RTC local usando la implementación existente (conocido comúnmente como OPCH [del inglés, "On Prem Config Hybrid" o modelo híbrido de configuración local]). Los usuarios de Microsoft Teams no se pueden habilitar para las funcionalidades de llamada RTC usando CCE u OPCH.

### <a name="interop-experiences-limitations"></a>Limitaciones de las experiencias de interoperabilidad
Actualmente, además de la falta de la presencia unificada en Microsoft Teams y Skype Empresarial, lo que provoca que Microsoft Teams y Skype Empresarial tengan sus propios estados de presencia independientes, hay algunas funciones que no están disponibles en las experiencias de interoperabilidad de chat y llamadas entre Microsoft Teams y Skype Empresarial.

A continuación se especifica la lista actual de limitaciones del chat con interoperabilidad:
- Las conversaciones (chats) entre varios participantes (grupo) en Microsoft Teams solo pueden incluir participantes que usen Microsoft Teams.
- Las conversaciones de MI (chats) de varios participantes en Skype Empresarial solo pueden incluir participantes que usen Skype Empresarial.
- No se admiten las transferencias de archivos en conversaciones de chat de dos participantes o el anexado de archivos en conversaciones de varias partes entre Microsoft Teams y Skype Empresarial, y viceversa.
- El chat con interoperabilidad no es persistente en Microsoft Teams.
- En Microsoft Teams, no se admiten en los chats con interoperabilidad Markdown, texto enriquecido, el conjunto completo de emoticonos, etc.

A continuación se especifica la lista actual de limitaciones de las llamadas con interoperabilidad:
- No se admite el uso compartido de pantalla (uso compartido de escritorio o aplicación) entre Microsoft Teams y Skype Empresarial.
- No se admite el escalado de una llamada en curso de par a par (P2P) de voz o vídeo a una llamada de varios participantes que incluya usuarios de Microsoft Teams y Skype Empresarial.

## <a name="managing-interoperability"></a>Administrar la interoperabilidad
Para administrar la interoperabilidad entre Microsoft Teams y Skype Empresarial se puede utilizar una nueva directiva llamada directiva de interoperabilidad de Microsoft Teams para controlar dónde enviar los chats y dirigir las llamadas (Microsoft Teams o Skype Empresarial). Esta directiva se puede configurar para todos los usuarios de la organización (directiva global), o aplicarse a usuarios individuales y administrarse a través de una sesión remota de Windows PowerShell en Skype Empresarial usando los cmdlets [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps).

De forma predeterminada, esta directiva está configurada para garantizar que Microsoft Teams y Skype Empresarial se pueden usar simultáneamente con una interoperabilidad mínima. Este enfoque pretende garantizar que las comunicaciones y los procesos empresariales actuales de su organización no se ven interrumpidos a causa de la adopción de Microsoft Teams.

### <a name="interop-policy-overview"></a>Información general de la directiva de interoperabilidad
La directiva de interoperabilidad de Microsoft Teams consta de los siguientes parámetros:

|Parámetro                    |Valores posibles      |Descripción  |
|-----------------------------|---------------------|---------|
|`ChatDefaultClient`          | Predeterminado, Skype Empresarial, Microsoft Teams | Este parámetro especifica la aplicación de chat predeterminada        |
|`CallingDefaultClient`       | Predeterminado, Skype Empresarial, Microsoft Teams | Este parámetro especifica la aplicación de llamadas predeterminada        |
|`AllowEndUserClientOverride` | True, False         | Este parámetro especifica si los usuarios pueden invalidar la aplicación de chat y llamadas predeterminada         |

> [!WARNING]
> Aunque es posible crear una directiva de interoperabilidad de Microsoft Teams con valores independientes para los parámetros `ChatDefaultClient` y `CallingDefaultClient`, esperamos que esto cambie en el futuro. De momento, asegúrese de utilizar el mismo valor para los dos parámetros.

#### <a name="chat-default-client"></a>Cliente de chat predeterminado
El parámetro `ChatDefaultClient` define cómo se dirigen los chats entre Microsoft Teams y Skype Empresarial, y el valor global predeterminado de este parámetro está establecido en **Default**.

> [!IMPORTANT]
> Actualmente, el parámetro `ChatDefaultClient` no se respeta en Microsoft Teams. Actualizaremos esta documentación para describir el comportamiento esperado cuando se respete este parámetro en Microsoft Teams. Las funcionalidades de interoperabilidad de chat existentes entre Microsoft Teams y Skype Empresarial controladas a nivel de inquilino seguirán funcionando del mismo modo.

#### <a name="calling-default-client"></a>Cliente de llamadas predeterminado
El parámetro `CallingDefaultClient` define cómo se dirigen las llamadas entre Microsoft Teams y Skype Empresarial, y el valor global predeterminado de este parámetro está establecido en **Default**.

A continuación se muestra una explicación detallada de cómo afecta cada ajuste de este parámetro al comportamiento del cliente de Microsoft Teams y Skype Empresarial.

|Autor de llamada llamando desde  |Ajuste: Default; llamada recibida en  |Ajuste: Teams; llamada recibida en  |Ajuste: SfB; llamada recibida en  |
|---------|---------|---------|---------|
|**Skype Empresarial**     |Skype Empresarial         |Microsoft Teams        |Skype Empresarial         |
|**Microsoft Teams**     |Microsoft Teams         |Microsoft Teams         |Skype Empresarial         |
|**RTC**   |Skype Empresarial        |Microsoft Teams        |Skype Empresarial         |
|**Skype Empresarial federado**     |Skype Empresarial         |Skype Empresarial         |Skype Empresarial         |

> [!IMPORTANT]
> Actualmente, cambiar `CallingDefaultClient` a Teams afectará también a las llamadas a teléfonos IP de Skype Empresarial. Las llamadas entrantes no se recibirán en los teléfonos y solo sonarán en los clientes de Microsoft Teams. Consulte [De Skype Empresarial a Microsoft Teams: mapa de ruta de las opciones](https://aka.ms/skype2teamsroadmap) para obtener información sobre compatibilidad con teléfonos SIP existentes.

#### <a name="allowing-user-choice"></a>Permitir que el usuario decida
El parámetro `AllowEndUserClientOverride` acepta valores booleanos (**TRUE** o **FALSE**) y, cuando está ajustado en **TRUE**, Microsoft Teams permitirá a los usuarios seleccionar dónde quieren recibir las llamadas (Microsoft Teams o Skype Empresarial), y los usuarios podrán cambiar su aplicación principal en cualquier momento.

![Opción de aplicación de llamadas preferida](media/Preferred_calling_application_option.png)

El valor predeterminado global para este parámetro es **FALSE**, con lo que los usuarios no podrán elegir su aplicación principal sin la intervención del administrador.

## <a name="teams-interop-policy-special-cases"></a>Casos especiales de la directiva de interoperabilidad de Microsoft Teams
Al asignar la directiva de interoperabilidad de Microsoft Teams, los usuarios que permanezcan en una implementación de Skype Empresarial local (en una topología de implementación mixta [híbrida]), los usuarios con voz híbrida (tanto mediante CCE como OPCH) y los usuarios con flujos de trabajo de Skype Empresarial especializados se consideran casos especiales, y es necesario prestar una atención especial a la directiva que se les asigna.

### <a name="policy-for-skype-for-business-on-premises-users"></a>Directiva para usuarios de Skype Empresarial local
En una topología de implementación mixta (híbrida), los usuarios que se encuentren en una implementación de Skype Empresarial local no deben tener nunca el valor Teams en los parámetros `ChatDefaultClient` y `CallingDefaultClient` de su directiva. Si fuese así, no podrán recibir chats ni llamadas. Use la siguiente definición de directiva para usuarios locales:

|Parámetro  |Valor  |
|---------|---------|
|`ChatDefaultClient`    |Default o SfB         |
|`CallingDefaultClient`     |Default o SfB         |
|`AllowEndUserClientOverride`     |False         |

> [!IMPORTANT]
> Al mover usuarios de Skype Empresarial Online a Skype Empresarial local o viceversa, debe asegurarse de que la directiva de interoperabilidad de Microsoft Teams asignada a los usuarios responde al comportamiento que se debe aplicar. Recuerde que los usuarios locales no se pueden configurar para usar Microsoft Teams como aplicación principal de chat y llamadas.

### <a name="policy-for-hybrid-voice-users-cce-or-opch"></a>Directiva para usuarios de voz híbrida (CCE u OPCH)
Los usuarios de Skype Empresarial Online habilitados para Sistema telefónico con voz híbrida (mediante CCE u OPCH) no pueden recibir llamadas RTC en Microsoft Teams. Al asignar la directiva de interoperabilidad de Microsoft Teams a los usuarios de voz híbrida, use la siguiente definición de directiva:

|Parámetro  |Valor  |
|---------|---------|
|`ChatDefaultClient`    |Default, SfB o Teams         |
|`CallingDefaultClient`     |Default o SfB         |
|`AllowEndUserClientOverride`     |False         |

### <a name="policy-for-users-with-specialized-skype-for-business-workflows"></a>Directiva para usuarios con flujos de trabajo de Skype Empresarial especializados
En algunos casos, es posible que un grupo de usuarios use aplicaciones de terceros que utilizan Skype Empresarial (p. ej., centros de llamadas, operadores de recepción, etc.). En estos casos, querrá asegurarse de que estos usuarios permanecen en Skype Empresarial hasta que tengan funcionalidades equivalentes en Microsoft Teams. Utilice la siguiente definición de directiva para estos usuarios:

|Parámetro  |Valor  |
|---------|---------|
|`ChatDefaultClient`    |Default o SfB         |
|`CallingDefaultClient`     |Default o SfB         |
|`AllowEndUserClientOverride`     |False         |