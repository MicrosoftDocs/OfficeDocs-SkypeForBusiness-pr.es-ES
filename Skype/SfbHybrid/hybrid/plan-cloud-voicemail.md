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
description: En este artículo se describen las ventajas, consideraciones de planeación y requisitos para implementar el servicio correo de voz en la nube de Microsoft. Para obtener información sobre cómo configurar el correo de voz en la nube, consulte Configuración del correo de voz en la nube.
ms.openlocfilehash: 8a75c670448cf69cf6d9d772c670c9451fd94f80
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662095"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planear el servicio de correo de voz en la nube para usuarios locales

## <a name="overview"></a>Información general

En este artículo se describen las ventajas, las consideraciones de planeación y los requisitos para implementar el servicio correo de voz en la nube de Microsoft para los usuarios locales. Para obtener información sobre cómo configurar el correo de voz en la nube, consulte Configurar el servicio de correo [de voz en la nube.](configure-cloud-voicemail.md)

El correo de voz en la nube ocupa el lugar de la mensajería unificada de Exchange al proporcionar la funcionalidad de mensajería de voz para los usuarios de voz de Skype Empresarial 2019 que tienen buzones en Exchange Server 2019 o Exchange Online. El correo de voz en la nube proporciona las siguientes ventajas para los usuarios locales y en línea:

- Funcionalidad de respuesta y depósito de correo de voz con transcripción de voz mejorada

- Acceso al correo de voz en el buzón de Exchange del usuario mediante los clientes de Skype Empresarial Online o Outlook

- La capacidad de usar el Centro de administración de Microsoft 365 para administrar las opciones de correo de voz

- Compatibilidad con buzones de Exchange locales o en la nube

- Aprovechar los saludos de usuario existentes de la mensajería unificada de Exchange Online

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual los usuarios ya no podrán acceder al correo de voz en su buzón de Exchange a través del cliente de Skype Empresarial Online.

Para obtener más información acerca de la comparación de características, consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Skype Empresarial Server 2019 sigue utilizando la mensajería unificada de Exchange para los usuarios cuyos buzones están en versiones anteriores de Exchange Server (2013, 2016).  Comprender qué solución de correo de voz se usará en función de la versión de Exchange Server y Skype Empresarial Server es una parte importante de la planeación de la migración a Skype Empresarial Server 2019 o Exchange Server 2019. Para obtener más información acerca de la migración y la interoperabilidad, consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Con el correo de voz en la nube, las tareas de administración se simplifican en gran medida porque:

- No es necesario configurar el rol de mensajería unificada de Exchange.
- Las tareas de configuración del correo de voz en la nube son más sencillas.
- Las actualizaciones de la funcionalidad del correo de voz se entregan directamente en la nube, por lo que los usuarios siempre tienen acceso a las últimas características y actualizaciones con menos dependencia en las actualizaciones acumulativas ( CPU).
- Tiene el mismo conjunto de controles para los buzones de Exchange locales y en línea. Para obtener más información sobre estos controles, vea [Configurar el correo de voz del sistema telefónico.](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)

En el siguiente diagrama se muestra el correo de voz en la nube en una implementación híbrida:

![Correo de voz en la nube de SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Las llamadas no contestadas se controlan de la siguiente manera:  

1. Para los usuarios que se encuentran en Skype Empresarial 2019 local, skype empresarial local envía llamadas no contestadas al servicio de correo de voz en la nube en línea.
2. El servicio procesa el correo de voz, incluida la transcripción.
3. A continuación, el servicio deposita el correo de voz en el buzón de Exchange del usuario, independientemente de si el buzón es local o en línea.  
4. Los usuarios pueden acceder a su correo de voz desde su cliente de Skype Empresarial o outlook.

## <a name="requirements"></a>Requirements

Los siguientes requisitos suponen que ya tiene Skype Empresarial Server implementado en una topología compatible.  Los requisitos dependen de su escenario:

- Si ya usa la mensajería unificada de Exchange online y actualiza a Skype Empresarial 2019, tendrá que modificar la directiva de correo de voz hospedado y comprobar que los proveedores de hospedaje están configurados correctamente. Para obtener más información, consulte [Configurar el servicio de correo de voz en la nube.](configure-cloud-voicemail.md)

- Si usa la mensajería unificada de Exchange local o tiene una combinación de usuarios que usan la mensajería unificada de Exchange en línea y local, necesitará modificar tanto la directiva de correo de voz hospedado como el proveedor de hospedaje.  Para obtener más información, consulte [Configurar el servicio de correo de voz en la nube.](configure-cloud-voicemail.md)

- Para obtener una nueva configuración de correo de voz en la nube, siga los pasos descritos en Configurar el servicio de correo [de voz en la nube.](configure-cloud-voicemail.md)

Además de los requisitos anteriores, los siguientes requisitos deben configurarse para conectarse al servicio correo de voz de Microsoft Cloud:

- Conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar el correo de voz en la nube para los usuarios locales, debe asegurarse de que tiene configurada la conectividad híbrida entre los entornos locales y en línea. A veces, esto se denomina configuración de dominio dividido.

   Para obtener más información, vea Planear la conectividad híbrida entre Skype Empresarial Server y [Microsoft 365 u Office 365](plan-hybrid-connectivity.md) y Configurar la conectividad híbrida entre Skype Empresarial Server y [Office 365.](configure-hybrid-connectivity.md)

- Los usuarios locales deben estar habilitados para Telefonía IP empresarial correo de voz hospedado en Skype Empresarial Server.

- Debe configurarse una dirección URL de servicios Web Exchange (EWS) externos y detección automática o algunas características de correo de voz en la nube estarán limitadas.

- Si tiene un servidor de Exchange local, configure el correo de voz en la nube con los pasos descritos en Configurar el correo de voz en la nube para Exchange Server [usuarios de buzones de correo.](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)

## <a name="migration-and-interoperability"></a>Migración e interoperabilidad

Si tiene previsto implementar Skype Empresarial Server 2019 o Exchange Server 2019, debe planear cuidadosamente la migración para garantizar que el servicio de mensajería de voz continúe. Tenga en cuenta lo siguiente:

- Exchange Server 2019 ya no proporciona funcionalidad de mensajería unificada de Exchange
- Skype Empresarial Server 2019 ya no se integra con la mensajería unificada de Exchange Online

La interoperabilidad de versiones y las topologías admitidas para el correo de voz en la nube se enumeran en la siguiente tabla, que compara las versiones de Skype Empresarial Server en las que el usuario podría hospedarse con la versión posible que proporciona su buzón de Exchange. Necesita usar correo de voz en la nube si desea usar Skype Empresarial 2019 con Exchange Online o Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype Empresarial Server 2019 | Exchange Server mensajería unificada | Exchange Server mensajería unificada | Correo de voz en la nube | Correo de voz en la nube |
| Skype Empresarial Server 2015 | Exchange Server mensajería unificada | Exchange Server mensajería unificada | No admitido | Correo de voz en la nube |
| Lync Server 2013 <br>  | Exchange Server mensajería unificada | Exchange Server mensajería unificada | No compatible | Correo de voz en la nube |

Microsoft recomienda las siguientes rutas de migración:

- Si va a actualizar a Skype Empresarial Server 2019, puede usar la mensajería unificada de Exchange en Exchange Server 2013 o 2016, pero debe actualizar a Correo de voz en la nube si usa Exchange Server 2019.
- Si está actualizando Exchange Server Exchange Server 2019 y está usando versiones anteriores de mensajería unificada de Exchange Server para mensajería de voz de Skype Empresarial Server, Microsoft recomienda actualizar a Skype Empresarial Server 2019 antes de la actualización del buzón.  De lo contrario, se perderán las capacidades de mensajería de voz.
- Si va a actualizar a Skype Empresarial Server 2019 y tiene Skype Empresarial Server 2015 configurado para el correo de voz con mensajería unificada de Exchange Online, el correo de voz de los usuarios migrará automáticamente de la mensajería unificada de Exchange Online al correo de voz en la nube cuando su cuenta se mueve a Skype Empresarial Server 2019. 

Para obtener más información acerca de la planeación de la migración, consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).
