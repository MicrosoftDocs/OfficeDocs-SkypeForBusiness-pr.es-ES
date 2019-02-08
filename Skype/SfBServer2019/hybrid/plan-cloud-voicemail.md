---
title: Planeación de servicio de correo de voz en la nube | PBX Skype para Business Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Este artículo describe las ventajas, las consideraciones de planeación y requisitos para implementar el servicio de correo de voz de Microsoft en la nube. Para obtener información acerca de cómo configurar el correo de voz en la nube, vea Configuración de correo de voz en la nube.
ms.openlocfilehash: e16ad9fb123342f7ac7e780f43bffd9b54b82ce6
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "29770918"
---
# <a name="plan-cloud-voicemail-service"></a>Planeación de servicio de correo de voz en la nube

## <a name="overview"></a>Información general

Este artículo describe las ventajas, las consideraciones de planeación y requisitos para implementar el servicio de correo de voz de Microsoft en la nube. Para obtener información acerca de cómo configurar el correo de voz en la nube, vea [servicio de configuración de correo de voz en la nube](configure-cloud-voicemail.md).

Correo de voz en la nube toma el lugar de Exchange mensajería unificada (UM) de proporcionar funcionalidad de mensajería de Skype para los usuarios de voz empresarial 2019 que tienen buzones en Exchange Server 2019 o Exchange Online de voz. Correo de voz en la nube proporciona las siguientes ventajas para los usuarios en línea y local:

- Funcionalidad de contestador automático y depósito de correo de voz con transcripción de voz mejorada

- Acceso al correo de voz en el buzón de Exchange del usuario mediante el uso de la Skype para clientes empresariales en línea o Outlook

- La capacidad de usar el portal de Office 365 basada en web para administrar las opciones de correo de voz

- Soporte técnico para los buzones de Exchange local o en la nube

- Aprovechamiento de los saludos de usuario existente de Online mensajería unificada de Exchange

Para obtener más información acerca de la comparación de características, consulte [Plan de Skype para Business Server y la migración de Exchange Server](plan-um-migration.md).

Skype para Business Server 2019 sigue utilizando mensajería unificada de Exchange para los usuarios cuyos buzones de correo se encuentran en las versiones anteriores de Exchange Server (2013, 2016).  Descripción de la solución de correo de voz se usará en función del servidor de Exchange y Skype para Business Server versión es una parte importante de la planeación de la migración a cualquiera Skype para Business Server 2019 o Exchange Server 2019. Para obtener más información acerca de la migración y la interoperabilidad, consulte [Plan de Skype para Business Server y la migración de Exchange Server](plan-um-migration.md).

Con correo de voz en la nube, las tareas de administración se simplifican en gran medida debido a que:

- No es necesario para configurar la función de mensajería unificada de Exchange.
- Las tareas de configuración para el correo de voz en la nube son más sencillas.
- Las actualizaciones a la funcionalidad de correo de voz se entregan directamente en la nube, por lo que los usuarios siempre tengan acceso a las últimas características y actualizaciones con menor dependencia en actualizaciones acumulativas (las actualizaciones acumulativas).
- Tienen el mismo conjunto de controles para los buzones de Exchange online y local. Para obtener más información sobre estos controles, vea [Configurar el correo de voz de sistema telefónico](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).

El siguiente diagrama muestra el correo de voz en la nube en una implementación híbrida:

![Correo de voz de SfB en la nube](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Las llamadas no respondidas se controlan de la siguiente manera:  

1. Para los usuarios alojados en Skype para profesionales 2019 en local, las llamadas no respondidas se envían por el Skype local para Business Server para el servicio de correo de voz en la nube en línea.
2. El servicio procesa el correo de voz, incluida la transcripción.
3. El servicio de depósitos, a continuación, el correo de voz en el buzón de Exchange del usuario, si el buzón de correo es local o en línea.  
4. Los usuarios pueden tener acceso a su correo de voz desde cualquiera su Skype para clientes empresariales o de Outlook.

## <a name="requirements"></a>Requisitos

Los siguientes requisitos se suponen que ya dispone de Skype para Business Server implementado en una topología admitida.  Los requisitos de dependen de su escenario:

- Si se ya está usando la mensajería unificada de Exchange online y actualizar a Skype para 2019 empresarial, debe modificar la directiva de correo de voz hospedado y comprobar que los proveedores de hospedaje se establecen correctamente. Para obtener más información, vea [servicio de configuración de correo de voz en la nube](configure-cloud-voicemail.md).

- Si está utilizando mensajería unificada de Exchange local, o si tiene una mezcla de los usuarios con mensajería unificada de Exchange en línea y local, se necesita modificar la directiva de correo de voz hospedado y el proveedor de hospedaje.  Para obtener más información, vea [servicio de configuración de correo de voz en la nube](configure-cloud-voicemail.md).

- Para una nueva configuración del correo de voz en la nube, siga los pasos descritos en el [servicio de configuración de correo de voz en la nube](configure-cloud-voicemail.md).

Además de los requisitos anteriores, la debajo de los requisitos de debe estar configurado para conectar con el servicio de correo de voz de la nube de Microsoft:

- Conectividad híbrida. Si ya dispone de Skype para Business Server implementado y que desea habilitar el correo de voz en la nube para los usuarios locales, debe asegurarse de que dispone de conectividad híbrida configurar entre los entornos en línea y local. En ocasiones, esto se denomina una configuración de dominio dividido.

   Para obtener más información, vea [Planear la conectividad híbrida entre Skype para Business Server y Office 365](plan-hybrid-connectivity.md) y [Configure la conectividad híbrida entre Skype para Business Server y Office 365](configure-hybrid-connectivity.md).

- Local a los usuarios deben estar habilitados para Enterprise Voice y correo de voz hospedado en Skype para Business Server.

- Un servicios de Web externo de Exchange (EWS) detección automática y la dirección URL deben configurar o algunas características de correo de voz en la nube estarán limitadas.

- Si tiene un deployment& de sólo local #x 2014; es decir, sólo Exchange y Skype para la empresa local servers& #x 2014; pero desea aprovechar las ventajas del correo de voz en la nube, no se necesitan licencias adicionales.

## <a name="migration-and-interoperability"></a>Migración e interoperabilidad

Si planea implementar Skype para Business Server 2019 o 2019 de Exchange Server, debe planear la migración con cuidado para garantizar la continuidad del servicio de mensajería de voz. Tenga en cuenta lo siguiente:

- Exchange Server 2019 ya no proporciona funcionalidad de mensajería unificada de Exchange
- Skype para Business Server 2019 ya no se integra con la mensajería unificada en línea

Interoperabilidad de versiones y las topologías admitidas para el correo de voz en la nube se enumeran en la tabla siguiente, que se compara el Skype para versiones de Business Server podría estar alojado en el usuario con la versión posible proporcionar su buzón de Exchange. Correo de voz en la nube solo funciona con Skype para Business Server y Exchange Server 2019 o Exchange Online.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype para Business Server 2019 | Servidor de mensajería unificada de Exchange | Servidor de mensajería unificada de Exchange | Correo de voz en la nube | Correo de voz en la nube
Skype Empresarial Server 2015 | Servidor de mensajería unificada de Exchange | Servidor de mensajería unificada de Exchange |  | Correo de voz en la nube <br> Exchange Online mensajería unificada * |
Lync Server 2013 <br>  | Servidor de mensajería unificada de Exchange | Servidor de mensajería unificada de Exchange | | Correo de voz en la nube <br> Exchange Online mensajería unificada * |

\*Hasta que en desuso. Para obtener más información, vea [migración de Exchange Unified Messaging Online admite](../plan/exchange-unified-messaging-online-migration-support.md) . 

Microsoft recomienda las siguientes rutas de acceso de migración:

- Si está actualizando a Skype para 2019 de servidor empresarial, puede utilizar mensajería unificada de Exchange en Exchange Server 2013 o 2016, pero debe actualizar al correo de voz en la nube si usa Exchange Server 2019.
- Si va a actualizar a Exchange Server 2019 y está utilizando las versiones anteriores del servidor de mensajería unificada de Exchange para Skype para la mensajería de voz de Business Server, Microsoft recomienda que actualice a Skype para Business Server 2019 antes de la actualización de buzón de correo.  De lo contrario, se perderá las capacidades de mensajería de voz.

Para obtener más información acerca de cómo planear la migración, consulte [Plan de Skype para Business Server y la migración de Exchange Server](plan-um-migration.md).
