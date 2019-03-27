---
title: 'Lync Server 2013: Administración de federación y el acceso externo a Skype para Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Habilitar y configurar el acceso de usuarios externos para controlar si los usuarios externos admitidos pueden colaborar con Skype interna para los usuarios de Business Server.
ms.openlocfilehash: c48914ca6dc7faf03fea1a3877bd2e349e39e290
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887861"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Administración de federación y el acceso externo a Skype para Business Server

Implementación de un servidor perimetral o grupo de servidores perimetrales es el primer paso para admitir usuarios externos. Para obtener información detallada sobre la implementación de los servidores perimetrales, vea [Implementar el servidor perimetral en Skype para Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Después de instalar y configurar la implementación interna de Skype para Business Server, los usuarios internos de la organización pueden colaborar con otros usuarios internos que tienen cuentas SIP de los servicios de dominio de Active Directory (AD DS). Colaboración puede incluir enviar y recibir mensajes instantáneos y actualización de estado de presencia y participar en conferencias (también conocido como "reuniones"). Habilitar y configurar el acceso de usuarios externos para controlar si los usuarios externos admitidos pueden colaborar con Skype interna para los usuarios de Business Server. Los usuarios externos pueden incluir los usuarios remotos de la implementación, los usuarios federados (incluidos usuarios compatibles de proveedores de servicios (IM) de la mensajería instantánea pública) y participantes anónimos en las conferencias.

Si su implementación incluye la instalación de un Skype para servidor perimetral de Business Server o un grupo de servidores perimetrales, el ámbito de los tipos de comunicación posibles se expande en gran medida con un número de opciones para el acceso de usuarios externos, la comunicación con los miembros de otro socios federados de SIP dominios y SIP proveedores federados. Después de configurar el servidor perimetral o grupo de servidores perimetrales, habilitar a los tipos de acceso de usuarios externos que desea proporcionar y configurar las directivas de control para el acceso externo. En Skype para Business Server, habilitar y configurar el acceso de usuarios externos y directivas mediante el Skype para el Panel de Control de servidor empresarial, la [Skype para Shell de administración de servidor empresarial](../management-shell.md), o ambos, según los requisitos de la tarea. 



> [!IMPORTANT]  
> Al diseñar la configuración y las directivas de acceso de usuarios externos, debe comprender la prioridad de las directivas y cómo se aplican las directivas. Skype para la configuración de directiva de Business Server que se aplican en un nivel de directiva puede invalidar la configuración que se aplica en el nivel de directiva de otra. Skype para la prioridad de la directiva de Business Server es: directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva Global (menos influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.


De forma predeterminada, no hay directivas están configurados para permitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, federados el acceso de usuarios, incluso si ya ha habilitado la compatibilidad con el acceso de usuarios externos para su organización. Para controlar el uso de acceso de usuarios externos, debe configurar una o varias directivas, que especifica el tipo de acceso de usuarios externos admitido para cada directiva. Esto incluye las siguientes directivas de acceso externo:

  - **Directiva global**   la directiva global se crea al implementar los servidores perimetrales. De forma predeterminada, no hay opciones de acceso de usuarios externos están habilitadas en la directiva global. Para permitir el acceso de usuarios externos en el nivel global, configure la directiva global para admitir uno o varios tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas de sitio y directivas de usuario reemplazan la directiva global. Si se elimina la directiva global, no lo quita. En su lugar, se restablece a la configuración predeterminada.

  - **Directiva de sitio**   puede crear y configurar una o más directivas de sitio para limitar la compatibilidad para el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilita el acceso de usuarios remotos para un sitio específico. De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de ese sitio, pero puede asignar una directiva de usuario a un usuario para invalidar la configuración de directiva de sitio.

  - **Directiva de usuario**   puede crear y configurar una o más directivas de usuario para limitar la compatibilidad para el acceso de usuarios remotos a usuarios específicos. La configuración en la la información global de invalidaciones de directivas de usuario y la directiva de sitio, pero sólo para los usuarios específicos a quien se asigna la directiva de usuario. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global y la directiva de sitio, es posible que especifique una directiva de usuario que deshabilita el acceso de usuarios remotos y, a continuación, asignar esa directiva de usuario a usuarios específicos. Si crea una directiva de usuario, se debe aplicar a uno o más usuarios para que surta efecto.

Para determinar qué opciones de configuración y las directivas que necesita crear o editar, consulte los siguientes puntos de decisión:

**¿Desea permitir que los usuarios internos y externos de su dominio puedan colaborar mediante mensajería instantánea, conferencias Web y Audio/vídeo?**

Configurar las opciones como se detalla en los temas [Configure directivas para controlar el acceso de usuarios remotos](external-access-policies/configure-policies-to-control-remote-user-access.md)y [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**¿Desea permitir a los usuarios anónimos asistan y sean invitados a conferencias hospedadas por los usuarios de la implementación?**

Configurar las opciones como se detalla en el tema [asignar directivas de conferencia para admitir usuarios anónimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) y [crear directivas de conferencia](../conferencing/create-policies.md).

**¿Desea permitir a los usuarios comunicarse con contactos de dominio federados SIP?**

Configurar las opciones como se detalla en los temas de [Configurar directivas de control de acceso de usuarios federados](external-access-policies/configure-policies-to-control-federated-user-access.md), [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)y [Administrar SIP federados dominios para la organización](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Si ha habilitado la comunicación con los dominios federados SIP, ¿desea habilitar la detección automática de federación SIP?**

Configurar las opciones como se detalla en el tema [Habilitar o deshabilitar la detección de los socios federados](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Si ha habilitado la comunicación con los dominios SIP de federación, ¿desea habilitar el envío de una renuncia de responsabilidad a contactos federados donde se notifica que usan el archivado y que es posible que se archivan las comunicaciones de?**

Configurar las opciones como se detalla en el tema [Habilitar o deshabilitar el envío de una renuncia de archivado a los socios federados en](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**¿Desea permitir a los usuarios comunicarse con proveedores federados SIP que habilitan la comunicación con proveedores públicos?**

Configure la configuración como se detalla en los temas [Configurar directivas a usuarios públicos de control de acceso](external-access-policies/configure-policies-to-control-public-user-access.md), [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)y [crear o editar pública proveedores federados de SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**¿Desea permitir a los usuarios comunicarse con proveedores federados SIP que son proveedores hospedados que ejecutan Microsoft Office 365 y Skype para profesionales en línea?**

Configurar las opciones como se detalla en los temas de [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) y [crear o editar hospedado proveedores federados de SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**¿Está configurada su implementación en un dominio dividido (también conocido como un híbrido), donde algunos usuarios tienen su servidor principal en una implementación local y otros usuarios están configuradas con un servidor principal en un entorno en línea?**

Configure la configuración como se detalla en los temas [Configure directivas para controlar el acceso de usuarios federados](external-access-policies/configure-policies-to-control-federated-user-access.md), [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)y [crear o editar hospedado proveedores federados de SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


Puede configurar la configuración de acceso de usuarios externos, incluidas las directivas que desea usar para controlar el acceso de usuarios externos, incluso si no ha habilitado el acceso de usuarios externos para su organización. Sin embargo, las directivas y otras opciones que configurar están en vigor sólo cuando tienen acceso de usuarios externos habilitado para la organización. Los usuarios externos no pueden comunicarse con los usuarios de su organización cuando se deshabilita el acceso de usuarios externos o si no hay directivas de acceso de usuarios externos están configuradas para que lo admitan.

La implementación perimetral autentica los tipos de usuarios externos (excepto para los usuarios anónimos, que son autenticados por el identificador de conferencia y una clave de paso que se envía al participante anónimo cuando crea la conferencia e invitación a participantes) y controles en función de cómo configurar su admitir servidores perimetrales de acceso. Con el fin de controlar las comunicaciones, puede configurar una o varias directivas y configurar las opciones que definen cómo los usuarios dentro y fuera de la implementación de comunican entre sí. Las directivas y configuración de incluir la directiva global predeterminada para el acceso de usuarios externos, además de las directivas de usuario y de sitio que se pueden crear y configurar para habilitar a uno o varios tipos de acceso de usuarios externos para sitios o usuarios específicos.

