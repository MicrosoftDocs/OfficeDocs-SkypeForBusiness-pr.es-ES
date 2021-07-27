---
title: Planear Correo de voz en la nube servicio para usuarios locales| PBX Skype Empresarial Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: En este artículo se describen las ventajas, consideraciones de planeación y requisitos para implementar el Correo de voz en la nube de Microsoft servicio. Para obtener información sobre cómo configurar Correo de voz en la nube, vea Configuring Correo de voz en la nube.
ms.openlocfilehash: cfde9867bcdd4c2b7492f8b50df782a5ca6fe34b
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509841"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planeación Correo de voz en la nube servicio para usuarios locales

## <a name="overview"></a>Información general

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este artículo se describen las ventajas, consideraciones de planeación y requisitos para implementar el servicio Correo de voz en la nube de Microsoft para los usuarios locales. Para obtener información sobre cómo configurar Correo de voz en la nube, vea [Configure Correo de voz en la nube service](configure-cloud-voicemail.md).

Correo de voz en la nube ocupa el lugar de la mensajería unificada (MU) de Exchange al proporcionar funcionalidad de mensajería de voz para usuarios de voz de Skype Empresarial 2019 que tienen buzones en Exchange Server 2019 o Exchange Online. Correo de voz en la nube proporciona las siguientes ventajas para los usuarios locales y en línea:

- Funcionalidad de contestador automático y depósito con transcripción de voz mejorada

- Acceso al correo de voz en el buzón de correo Exchange usuario mediante el Skype Empresarial online o Outlook cliente

- La capacidad de usar el Centro de administración de Microsoft 365 para administrar opciones de correo de voz

- Compatibilidad con Exchange buzones de correo locales o en la nube

- Aprovechar los saludos de usuario existentes desde Exchange Online mensajería unificada

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021, después de lo cual los usuarios ya no podrán acceder al correo de voz en su buzón de correo Exchange través del cliente de Skype Empresarial Online.

Para obtener más información acerca de la comparación de características, [vea Plan for Skype Empresarial Server and Exchange Server migration](plan-um-migration.md).

Skype Empresarial Server 2019 sigue utilizando la mensajería unificada Exchange usuarios cuyos buzones se encuentran en versiones anteriores de Exchange Server (2013, 2016).  Comprender qué solución de correo de voz se usará en función de la versión Exchange Server y Skype Empresarial Server es una parte importante de la planeación de la migración a Skype Empresarial Server 2019 o Exchange Server 2019. Para obtener más información acerca de la migración y la interoperabilidad, [vea Plan for Skype Empresarial Server and Exchange Server migration](plan-um-migration.md).

Con Correo de voz en la nube, las tareas de administración se simplifican en gran medida porque:

- No es necesario configurar el rol Exchange de mensajería unificada.
- Las tareas de configuración para Correo de voz en la nube son más sencillas.
- Las actualizaciones de la funcionalidad del correo de voz se entregan directamente en la nube, por lo que los usuarios siempre tienen acceso a las últimas características y actualizaciones con menos dependencia de las actualizaciones acumulativas ( CPU).
- Tiene el mismo conjunto de controles para buzones de correo locales y Exchange en línea. Para obtener más información sobre estos controles, vea [Configurar Sistema telefónico correo de voz](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).

El siguiente diagrama muestra Correo de voz en la nube en una implementación híbrida:

![SfB Correo de voz en la nube](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Las llamadas sin respuesta se controlan de la siguiente manera:  

1. Para los usuarios que se hospedaron en Skype Empresarial 2019 localmente, las llamadas no contestadas se envían mediante el Skype Empresarial Server local al servicio de Correo de voz en la nube en línea.
2. El servicio procesa el correo de voz, incluida la transcripción.
3. A continuación, el servicio deposita el correo de voz en el Exchange del usuario, independientemente de si el buzón es local o en línea.  
4. Los usuarios pueden acceder a su correo de voz desde su Skype Empresarial o Outlook cliente.

## <a name="requirements"></a>Requisitos

Los siguientes requisitos suponen que ya Skype Empresarial Server implementado en una topología compatible.  Los requisitos dependen del escenario:

- Si ya está usando Exchange mensajería unificada en línea y actualiza a Skype Empresarial 2019, deberá modificar la directiva de correo de voz hospedado y comprobar que los proveedores de hospedaje están configurados correctamente. Para obtener más información, vea [Configure Correo de voz en la nube service](configure-cloud-voicemail.md).

- Si usa una mensajería unificada local Exchange o tiene una combinación de usuarios que usan Exchange mensajería unificada en línea y local, necesitará modificar tanto la directiva de correo de voz hospedada como el proveedor de hospedaje.  Para obtener más información, vea [Configure Correo de voz en la nube service](configure-cloud-voicemail.md).

- Para una nueva configuración de Correo de voz en la nube, siga los pasos descritos en [Configure Correo de voz en la nube service](configure-cloud-voicemail.md).

Además de los requisitos anteriores, los siguientes requisitos deben configurarse para conectarse al Correo de voz en la nube de Microsoft servicio:

- Conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar Correo de voz en la nube para los usuarios locales, debe asegurarse de que tiene la conectividad híbrida configurada entre los entornos locales y los entornos en línea. A veces se denomina configuración de dominio dividido.

   Para obtener más información, vea [Plan hybrid connectivity between Skype Empresarial Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) y Configure hybrid connectivity between Skype Empresarial Server and [Office 365](configure-hybrid-connectivity.md).

- Los usuarios locales deben estar habilitados para Telefonía IP empresarial correo de voz hospedado en Skype Empresarial Server.

- Se debe configurar una dirección URL Exchange Web Services (EWS) y la detección automática, o bien algunas Correo de voz en la nube características serán limitadas.

- Si tiene un servidor de Exchange local, configure Correo de voz en la nube con los pasos descritos en Configurar Correo de voz en la nube para Exchange Server [de buzones](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)de correo .

## <a name="migration-and-interoperability"></a>Migración e interoperabilidad

Si tiene previsto implementar Skype Empresarial Server 2019 o Exchange Server 2019, debe planear cuidadosamente la migración para garantizar que el servicio de mensajería de voz continúe. Tenga en cuenta lo siguiente:

- Exchange Server 2019 ya no proporciona Exchange funcionalidad de mensajería unificada
- Skype Empresarial Server 2019 ya no se integra con Exchange Online mensajería unificada

La interoperabilidad de versiones y las topologías admitidas para Correo de voz en la nube se enumeran en la tabla siguiente, que compara las versiones de Skype Empresarial Server en las que el usuario podría hospedarse con la versión posible que proporciona su buzón de correo Exchange. Debe usar Correo de voz en la nube si desea usar Skype Empresarial 2019 con Exchange Online o Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype Empresarial Server 2019 | Exchange Server MENSAJERÍA UNIFICADA | Exchange Server MENSAJERÍA UNIFICADA | Correo de voz en la nube | Correo de voz en la nube |
| Skype Empresarial Server 2015 | Exchange Server MENSAJERÍA UNIFICADA | Exchange Server MENSAJERÍA UNIFICADA | No admitido | Correo de voz en la nube |
| Lync Server 2013 <br>  | Exchange Server MENSAJERÍA UNIFICADA | Exchange Server MENSAJERÍA UNIFICADA | No compatible | Correo de voz en la nube |

Microsoft recomienda las siguientes rutas de migración:

- Si está actualizando Skype Empresarial Server Skype Empresarial Server 2019, puede usar la mensajería unificada de Exchange en Exchange Server 2013 o 2016, pero debe actualizar a Correo de voz en la nube si usa Exchange Server 2019.
- Si actualiza Exchange Server Exchange Server 2019 y usa versiones anteriores de mensajería unificada de Exchange Server para mensajería de voz Skype Empresarial Server, Microsoft recomienda actualizar Skype Empresarial Server Skype Empresarial Server 2019 antes de la actualización del buzón.  De lo contrario, se perderán las capacidades de mensajería de voz.
- Si está actualizando Skype Empresarial Server Skype Empresarial Server 2019 y tiene Skype Empresarial Server 2015 configurado para correo de voz con mensajería unificada Exchange Online, el correo de voz de los usuarios migrará automáticamente de una mensajería unificada Exchange Online Correo de voz en la nube cuando su cuenta se mueve Skype Empresarial Server Skype Empresarial Server 2019. 

Para obtener más información acerca de la planeación de la migración, [vea Plan for Skype Empresarial Server and Exchange Server migration](plan-um-migration.md).