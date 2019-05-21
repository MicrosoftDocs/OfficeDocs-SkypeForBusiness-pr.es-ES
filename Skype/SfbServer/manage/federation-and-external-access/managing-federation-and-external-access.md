---
title: 'Lync Server 2013: administración de la Federación y el acceso externo a Skype empresarial Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede habilitar y configurar el acceso de usuarios externos para controlar si los usuarios externos compatibles pueden colaborar con usuarios internos de Skype empresarial Server.
ms.openlocfilehash: 555fa5ca08a707f09c9e33d8b98294b7bb584046
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280106"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Administración de la Federación y el acceso externo a Skype empresarial Server

Implementar un servidor perimetral o un grupo perimetral es el primer paso para admitir usuarios externos. Para obtener detalles sobre la implementación de servidores perimetrales, consulte [implementar el servidor perimetral en Skype empresarial Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Después de instalar y configurar la implementación interna de Skype empresarial Server, los usuarios internos de su organización pueden colaborar con otros usuarios internos que tengan cuentas SIP en los servicios de dominio de Active Directory (AD DS). La colaboración puede incluir el envío y la recepción de mensajes instantáneos, así como la actualización del estado de presencia y la participación en conferencias (también conocidas como "reuniones"). Puede habilitar y configurar el acceso de usuarios externos para controlar si los usuarios externos compatibles pueden colaborar con usuarios internos de Skype empresarial Server. Los usuarios externos pueden incluir usuarios remotos de su implementación, usuarios federados (incluidos los usuarios admitidos de proveedores de servicios de mensajería instantánea pública) y participantes anónimos en conferencias.

Si su implementación incluía la instalación de un servidor perimetral de Skype empresarial Server o un grupo Edge, el ámbito de los posibles tipos de comunicación se ha ampliado enormemente con una serie de opciones para el acceso de usuarios externos, la comunicación con miembros de otro SIP federado Dominios y proveedores federados de SIP. Después de configurar el servidor perimetral o el grupo perimetral, habilite los tipos de acceso de usuarios externos que desea proporcionar y configure las directivas para controlar el acceso externo. En Skype empresarial Server, puede habilitar y configurar directivas y acceso a usuarios externos con el panel de control de Skype empresarial Server, el [Shell de administración de Skype empresarial Server](../management-shell.md), o ambos, en función de los requisitos de la tarea. 



> [!IMPORTANT]  
> Al diseñar la configuración y las directivas para el acceso de usuarios externos, debe comprender la prioridad de las directivas y cómo se aplican las directivas. La configuración de directiva de Skype empresarial Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de servidor de Skype empresarial es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.


De forma predeterminada, ninguna directiva está configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad de acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos admitido para cada Directiva. Esto incluye las siguientes directivas de acceso externo:

  - **Directiva global se**   crea la directiva global al implementar los servidores perimetrales. De forma predeterminada, no hay ninguna opción de acceso de usuario externo habilitada en la directiva global. Para admitir el acceso de usuarios externos en el nivel global, configure la directiva global para que admita uno o varios tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas del sitio y las directivas de usuario invalidan la directiva global. Si elimina la directiva global, no la quitará. En su lugar, lo restablecerá a la configuración predeterminada.

  - **Directiva de sitio**   puede crear y configurar una o varias directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico. De forma predeterminada, se aplica una directiva de sitio a todos los usuarios de ese sitio, pero puede asignar una directiva de usuario a un usuario para que anule la configuración de directiva de sitio.

  - **Directiva de usuario**   puede crear y configurar una o más directivas de usuario para limitar la compatibilidad del acceso de usuarios remotos a usuarios específicos. La configuración de la Directiva de usuario reemplaza la directiva global y la de sitio, pero solo para los usuarios específicos a los que se asigna la Directiva de usuario. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global y la Directiva de sitio, puede especificar una directiva de usuario que deshabilite el acceso de usuarios remotos y, a continuación, asignar esa Directiva de usuario a usuarios específicos. Si crea una directiva de usuario, debe aplicarla a uno o más usuarios para que tenga efecto.

Para determinar qué opciones de configuración y qué directivas necesita crear o editar, consulte los siguientes puntos de decisión:

**¿Desea permitir que los usuarios internos y externos de su dominio puedan colaborar con la mensajería instantánea, las conferencias web y el audio/vídeo?**

Configure las opciones tal y como se detalla en los temas [configurar directivas para controlar el accesible a los usuarios remotos](external-access-policies/configure-policies-to-control-remote-user-access.md)y [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**¿Desea permitir que los usuarios anónimos asistan e inviten a conferencias hospedadas por los usuarios de su implementación?**

Configure las opciones que se detallan en el tema [asignar directivas de conferencia para admitir usuarios anónimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) y [crear directivas de conferencia](../conferencing/create-policies.md).

**¿Desea permitir que los usuarios se comuniquen con los contactos de dominios federados de SIP?**

Configure las opciones que se detallan en los temas [configurar directivas para controlar el acceso de usuarios federados](external-access-policies/configure-policies-to-control-federated-user-access.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), y [administrar dominios federados SIP para su organización](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Si ha habilitado la comunicación con dominios federados SIP, ¿desea habilitar la detección automática de la Federación SIP?**

Configure las opciones que se detallan en el tema [habilitar o deshabilitar la detección de socios de Federación](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Si ha habilitado la comunicación con dominios de Federación SIP, ¿desea habilitar el envío de un aviso de declinación de responsabilidades a los contactos federados para notificarles que usa el archivado y que las comunicaciones pueden archivarse?**

Configure las opciones que se detallan en el tema [habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**¿Desea permitir que los usuarios se comuniquen con proveedores federados SIP que permitan la comunicación con proveedores públicos?**

Configure las opciones que se detallan en los temas [configurar directivas para controlar el acceso de usuarios públicos](external-access-policies/configure-policies-to-control-public-user-access.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), y [crear o editar proveedores federados de SIP pública](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**¿Desea permitir que los usuarios se comuniquen con proveedores federados SIP que sean proveedores alojados que ejecuten Microsoft Office 365 y Skype empresarial online?**

Configure las opciones de configuración que se detallan en los temas [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) y [crear o editar proveedores federados de SIP hospedado](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**¿La implementación está configurada en un dominio dividido (también conocido como híbrido), en el que algunos usuarios tienen su servidor principal en una implementación local y otros usuarios están configurados con un servidor principal en un entorno en línea?**

Configure las opciones que se detallan en los temas [configurar directivas para controlar el acceso de usuarios federados](external-access-policies/configure-policies-to-control-federated-user-access.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), y [crear o modificar proveedores federados de SIP hospedados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


Puede configurar la configuración de acceso de usuarios externos, incluidas las directivas que desee usar para controlar el acceso de usuarios externos, incluso si no ha habilitado el acceso de usuarios externos para su organización. Sin embargo, las directivas y otras opciones de configuración que se configuran solo estarán vigentes cuando tenga habilitado el acceso de usuarios externos a su organización. Los usuarios externos no pueden comunicarse con los usuarios de su organización cuando el acceso de usuarios externos está deshabilitado o si ninguna directiva de acceso de usuarios externos está configurada para admitirlo.

La implementación de Edge autentica los tipos de usuarios externos (excepto para los usuarios anónimos, que son autenticados por el identificador de conferencia y una clave de paso que se envía al participante anónimo al crear la Conferencia e invitar a participantes) y controles acceso según la configuración de la compatibilidad de los extremos. Para controlar las comunicaciones, puede configurar una o varias directivas y configurar opciones que definan cómo los usuarios de dentro y fuera de la implementación se comunican entre sí. Las directivas y la configuración incluyen la directiva global predeterminada para el acceso de usuarios externos, además de las directivas de sitio y de usuario que puede crear y configurar para habilitar uno o varios tipos de acceso de usuarios externos para determinados sitios o usuarios.

