---
title: Planear el servicio de correo de voz en la nube para usuarios locales | PBX Skype empresarial Server 2019
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
description: En este artículo se describen las ventajas, las consideraciones de planeación y los requisitos para implementar el servicio de correo de voz en la nube de Microsoft. Para obtener información sobre cómo configurar el correo de voz de nube, consulte Configurar el correo de voz de nube.
ms.openlocfilehash: 8a75c670448cf69cf6d9d772c670c9451fd94f80
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662095"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planear el servicio de correo de voz en la nube para usuarios locales

## <a name="overview"></a>Información general

En este artículo se describen las ventajas, las consideraciones de planeación y los requisitos para implementar el servicio de correo de voz de la nube de Microsoft para los usuarios locales. Para obtener información sobre cómo configurar el correo de voz de nube, consulte [configurar el servicio de correo de voz de nube](configure-cloud-voicemail.md).

El correo de voz de nube asume el espacio de mensajería unificada (UM) de Exchange al ofrecer funcionalidad de mensajes de voz para los usuarios de voz de Skype empresarial 2019 que tienen buzones en Exchange Server 2019 o Exchange Online. El correo de voz de nube proporciona las siguientes ventajas tanto para los usuarios locales como en los en línea:

- Respuesta del correo de voz y funcionalidad de depósito con transcripción de voz mejorada

- Acceso al correo de voz en el buzón de Exchange del usuario mediante los clientes de Skype empresarial online o Outlook

- La capacidad de usar el centro de administración de Microsoft 365 para administrar las opciones de correo de voz

- Soporte para buzones de Exchange en local o en la nube

- Aprovechar los saludos de usuario existentes de la mensajería unificada de Exchange Online

> [!Important]
> Skype empresarial online se retirará el 31 de julio de 2021 después de lo cual los usuarios ya no podrán acceder al correo de voz en su buzón de Exchange a través del cliente de Skype empresarial online.

Para obtener más información acerca de la comparación de características, consulte [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

Skype empresarial Server 2019 sigue usando la mensajería unificada de Exchange para los usuarios cuyos buzones se encuentran en versiones anteriores de Exchange Server (2013, 2016).  Comprender qué solución de correo de voz se usará en función de Exchange Server y de la versión de Skype empresarial Server es una parte importante de la planeación de la migración a Skype empresarial Server 2019 o Exchange Server 2019. Para obtener más información acerca de la migración y la interoperabilidad, consulte [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

Con el correo de voz de la nube, las tareas de administración se simplifican enormemente porque:

- No es necesario configurar el rol de mensajería unificada de Exchange.
- Las tareas de configuración para el correo de voz de nube son más sencillas.
- Las actualizaciones de la funcionalidad de correo de voz se entregan directamente en la nube, por lo que los usuarios siempre tienen acceso a las últimas características y actualizaciones con menos dependencia en las actualizaciones acumulativas (CUs).
- Tiene el mismo conjunto de controles para los buzones de Exchange locales y en línea. Para obtener más información sobre estos controles, consulte [configurar el correo de voz del sistema telefónico](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).

El siguiente diagrama muestra el correo de voz de nube en una implementación híbrida:

![Correo de voz de nube de SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Las llamadas no respondidas se administran de la siguiente manera:  

1. Para los usuarios hospedados en Skype empresarial 2019 local, las llamadas no respondidas se envían por el servidor local de Skype empresarial Server al servicio de correo de voz en la nube en línea.
2. El servicio procesa el correo de voz, incluida la transcripción.
3. A continuación, el servicio deposita el correo de voz en el buzón de correo de Exchange del usuario, independientemente de si el buzón de correo es local o en línea.  
4. Los usuarios pueden obtener acceso al correo de voz desde el cliente de Skype empresarial o de Outlook.

## <a name="requirements"></a>Requirements

En los siguientes requisitos se da por supuesto que ya ha implementado Skype empresarial Server en una topología compatible.  Sus requisitos dependen de su escenario:

- Si ya usa la mensajería unificada en línea de Exchange y actualiza a Skype empresarial 2019, tendrá que modificar la Directiva de correo de voz hospedado y comprobar que los proveedores de hospedaje estén correctamente configurados. Para obtener más información, consulte [configurar el servicio de correo de voz en la nube](configure-cloud-voicemail.md).

- Si usa la mensajería unificada de Exchange local o tiene una mezcla de usuarios que usan la mensajería unificada de Exchange en línea y local, necesitará modificar la Directiva de correo de voz hospedado y el proveedor de hospedaje.  Para obtener más información, consulte [configurar el servicio de correo de voz en la nube](configure-cloud-voicemail.md).

- Para una nueva configuración del correo de voz de la nube, siga los pasos descritos en [configurar el servicio de correo de voz en la nube](configure-cloud-voicemail.md).

Además de los requisitos anteriores, deben configurarse los siguientes requisitos para conectarse al servicio de correo de voz de la nube de Microsoft:

- Conectividad híbrida. Si ya ha implementado Skype empresarial Server y desea habilitar el correo de voz de la nube para los usuarios locales, debe asegurarse de que tiene una conectividad híbrida configurada entre su entorno local y el entorno en línea. A veces, se denomina configuración de dominio dividido.

   Para obtener más información, vea [plan Hybrid Connectivity between Skype for Business Server y Microsoft 365 u office 365](plan-hybrid-connectivity.md) y [configurar la conectividad híbrida entre Skype empresarial server y Office 365](configure-hybrid-connectivity.md).

- Los usuarios locales deben estar habilitados para telefonía IP empresarial y correo de voz hospedado en Skype empresarial Server.

- Una dirección URL externa de servicios web Exchange (EWS) y la detección automática deben estar configuradas o algunas características de correo de voz de la nube estarán limitadas.

- Si tiene un servidor de Exchange local, configure el correo de voz de la nube siguiendo los pasos de [configurar el correo de voz de nube para usuarios de buzones de correo de Exchange Server](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).

## <a name="migration-and-interoperability"></a>Migración e interoperabilidad

Si tiene previsto implementar Skype empresarial Server 2019 o Exchange Server 2019, debe planear la migración con cuidado para garantizar el servicio continuo para la mensajería de voz. Tenga en cuenta lo siguiente:

- Exchange Server 2019 ya no proporciona funcionalidad de mensajería unificada de Exchange
- Skype empresarial Server 2019 ya no se integra con la mensajería unificada de Exchange Online

La interoperabilidad de versiones y las topologías admitidas para el correo de voz de la nube se enumeran en la siguiente tabla, que compara las versiones de Skype empresarial Server en las que el usuario puede estar alojado, con la versión posible que proporciona el buzón de Exchange. Debe usar el correo de voz de nube si desea usar Skype empresarial 2019 con Exchange online o Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange en línea   |
|:---    |:--- |:--- |:--- |:---  |
| Skype Empresarial Server 2019 | Mensajería unificada de Exchange Server | Mensajería unificada de Exchange Server | Correo de voz en la nube | Correo de voz en la nube |
| Skype Empresarial Server 2015 | Mensajería unificada de Exchange Server | Mensajería unificada de Exchange Server | No admitido | Correo de voz en la nube |
| Lync Server 2013 <br>  | Mensajería unificada de Exchange Server | Mensajería unificada de Exchange Server | No compatible | Correo de voz en la nube |

Microsoft recomienda las siguientes rutas de migración:

- Si va a actualizar a Skype empresarial Server 2019, puede usar la mensajería unificada de Exchange en Exchange Server 2013 o 2016, pero debe actualizar al correo de voz de la nube si usa Exchange Server 2019.
- Si va a actualizar a Exchange Server 2019 y está usando versiones anteriores de la mensajería UNIFICAda de Exchange Server para los mensajes de voz de Skype empresarial Server, Microsoft le recomienda que actualice a Skype empresarial Server 2019 antes de la actualización del buzón de correo.  De lo contrario, se perderán las funciones de mensajería de voz.
- Si va a actualizar a Skype empresarial Server 2019 y tiene Skype empresarial Server 2015 configurado para correo de voz con mensajería unificada de Exchange Online, el correo de voz de los usuarios migrará automáticamente de la mensajería unificada de Exchange Online al correo de voz de la nube cuando su cuenta se mueva a Skype empresarial Server 2019. 

Para obtener más información acerca de la planeación de la migración, vea [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).
