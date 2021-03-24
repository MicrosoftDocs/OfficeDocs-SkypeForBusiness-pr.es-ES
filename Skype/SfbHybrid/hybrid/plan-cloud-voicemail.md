---
title: Planear el servicio de correo de voz en la nube para usuarios locales| PBX Skype Empresarial Server 2019
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
description: En este artículo se describen las ventajas, consideraciones de planeación y requisitos para implementar el servicio de correo de voz en la nube de Microsoft. Para obtener información sobre la configuración del correo de voz en la nube, consulte Configuring Cloud Voicemail.
ms.openlocfilehash: 4ae274f33d2b7d52c486cd9031d01bc3a532a6b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110286"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planear el servicio de correo de voz en la nube para usuarios locales

## <a name="overview"></a>Información general

En este artículo se describen las ventajas, consideraciones de planeación y requisitos para implementar el servicio de correo de voz de Microsoft Cloud para los usuarios locales. Para obtener información sobre la configuración del correo de voz en la nube, vea [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

El correo de voz en la nube ocupa el lugar de la mensajería unificada (MU) de Exchange al proporcionar funcionalidad de mensajería de voz para los usuarios de voz de Skype Empresarial 2019 que tienen buzones en Exchange Server 2019 o Exchange Online. El correo de voz en la nube proporciona las siguientes ventajas para los usuarios locales y en línea:

- Funcionalidad de contestador automático y depósito con transcripción de voz mejorada

- Acceso al correo de voz en el buzón de Exchange del usuario mediante los clientes de Skype Empresarial Online o Outlook

- La capacidad de usar el Centro de administración de Microsoft 365 para administrar opciones de correo de voz

- Compatibilidad con buzones de Exchange locales o en la nube

- Aprovechar los saludos de usuario existentes de la mensajería unificada de Exchange Online

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual los usuarios ya no podrán acceder al correo de voz en su buzón de Exchange a través del cliente de Skype Empresarial Online.

Para obtener más información acerca de la comparación de características, vea [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Skype Empresarial Server 2019 sigue utilizando la mensajería unificada de Exchange para usuarios cuyos buzones se encuentran en versiones anteriores de Exchange Server (2013, 2016).  Comprender qué solución de correo de voz se usará en función de la versión de Exchange Server y Skype Empresarial Server es una parte importante de la planeación de la migración a Skype Empresarial Server 2019 o Exchange Server 2019. Para obtener más información acerca de la migración y la interoperabilidad, vea [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Con el correo de voz en la nube, las tareas de administración se simplifican en gran medida porque:

- No es necesario configurar el rol de mensajería unificada de Exchange.
- Las tareas de configuración del correo de voz en la nube son más sencillas.
- Las actualizaciones de la funcionalidad del correo de voz se entregan directamente en la nube, por lo que los usuarios siempre tienen acceso a las últimas características y actualizaciones con menos dependencia de las actualizaciones acumulativas ( CPU).
- Tiene el mismo conjunto de controles para buzones locales y en línea de Exchange. Para obtener más información sobre estos controles, vea [Configurar el correo de voz del sistema telefónico.](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)

El siguiente diagrama muestra El correo de voz en la nube en una implementación híbrida:

![SfB Cloud Voicemail](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Las llamadas sin respuesta se controlan de la siguiente manera:  

1. Para los usuarios que se encuentran en Skype Empresarial 2019 local, el Skype Empresarial Server local envía llamadas sin respuesta al servicio de correo de voz en la nube en línea.
2. El servicio procesa el correo de voz, incluida la transcripción.
3. A continuación, el servicio deposita el correo de voz en el buzón de Exchange del usuario, independientemente de si el buzón es local o en línea.  
4. Los usuarios pueden acceder a su correo de voz desde su cliente de Skype Empresarial o outlook.

## <a name="requirements"></a>Requisitos

Los siguientes requisitos suponen que ya tiene Skype Empresarial Server implementado en una topología compatible.  Los requisitos dependen del escenario:

- Si ya está usando la mensajería unificada de Exchange online y actualiza a Skype Empresarial 2019, tendrá que modificar la directiva de correo de voz hospedada y comprobar que los proveedores de hospedaje están configurados correctamente. Para obtener más información, vea [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Si usa la mensajería unificada de Exchange localmente o tiene una combinación de usuarios que usan mensajería unificada de Exchange en línea y local, necesitará modificar tanto la directiva de correo de voz hospedada como el proveedor de hospedaje.  Para obtener más información, vea [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Para obtener una nueva configuración de Correo de voz en la nube, siga los pasos descritos en [Configurar el servicio de correo de voz en la nube.](configure-cloud-voicemail.md)

Además de los requisitos anteriores, los siguientes requisitos deben configurarse para conectarse al servicio de correo de voz en la nube de Microsoft:

- Conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar el correo de voz en la nube para los usuarios locales, debe asegurarse de que tiene la conectividad híbrida configurada entre sus entornos locales y en línea. A veces se denomina configuración de dominio dividido.

   Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 u Office 365](plan-hybrid-connectivity.md) y [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).

- Los usuarios locales deben estar habilitados para Telefonía IP empresarial correo de voz hospedado en Skype Empresarial Server.

- Se debe configurar una dirección URL de servicios web externos de Exchange (EWS) y detección automática o algunas características de correo de voz en la nube serán limitadas.

- Si tiene un servidor de Exchange local, configure Cloud Voicemail con los pasos descritos en Configurar el correo de voz en la nube [para Exchange Server usuarios de buzones](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)de correo .

## <a name="migration-and-interoperability"></a>Migración e interoperabilidad

Si planea implementar Skype Empresarial Server 2019 o Exchange Server 2019, debe planear cuidadosamente la migración para garantizar un servicio continuo de mensajería de voz. Tenga en cuenta lo siguiente:

- Exchange Server 2019 ya no proporciona funcionalidad de mensajería unificada de Exchange
- Skype Empresarial Server 2019 ya no se integra con la mensajería unificada de Exchange Online

La interoperabilidad de versiones y las topologías admitidas para el correo de voz en la nube se enumeran en la siguiente tabla, que compara las versiones de Skype Empresarial Server en las que el usuario podría hospedarse con la versión posible que proporciona su buzón de Exchange. Debe usar el correo de voz en la nube si desea usar Skype Empresarial 2019 con Exchange Online o Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype Empresarial Server 2019 | Exchange Server UM | Exchange Server UM | Correo de voz en la nube | Correo de voz en la nube |
| Skype Empresarial Server 2015 | Exchange Server UM | Exchange Server UM | No admitido | Correo de voz en la nube |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | No compatible | Correo de voz en la nube |

Microsoft recomienda las siguientes rutas de migración:

- Si va a actualizar a Skype Empresarial Server 2019, puede usar la mensajería unificada de Exchange en Exchange Server 2013 o 2016, pero debe actualizar a Correo de voz en la nube si usa Exchange Server 2019.
- Si actualiza Exchange Server Exchange Server 2019 y usa versiones anteriores de mensajería unificada de Exchange Server para mensajería de voz de Skype Empresarial Server, Microsoft recomienda actualizar a Skype Empresarial Server 2019 antes de la actualización del buzón.  De lo contrario, se perderán las capacidades de mensajería de voz.
- Si va a actualizar a Skype Empresarial Server 2019 y tiene Skype Empresarial Server 2015 configurado para el correo de voz con mensajería unificada de Exchange Online, el correo de voz de los usuarios migrará automáticamente de mensajería unificada de Exchange Online a correo de voz en la nube cuando se mueve su cuenta a Skype Empresarial Server 2019. 

Para obtener más información acerca de la planeación de la migración, vea [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).