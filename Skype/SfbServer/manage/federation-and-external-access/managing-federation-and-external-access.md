---
title: 'Lync Server 2013: Administrar la federación y el acceso externo a Skype Empresarial Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede habilitar y configurar el acceso de usuarios externos para controlar si los usuarios externos admitidos pueden colaborar con usuarios internos de Skype Empresarial Server.
ms.openlocfilehash: df8ca25dcaffb9ee563691eb327dc9ea6e9a229c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826610"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Administración de la federación y el acceso externo a Skype Empresarial Server

La implementación de un servidor perimetral o de un grupo de servidores perimetrales es el primer paso para la compatibilidad con usuarios externos. Para obtener más información acerca de la implementación de servidores perimetrales, consulte Implementar el servidor [perimetral en Skype Empresarial Server.](../../deploy/deploy-edge-server/deploy-edge-server.md)

Después de instalar y configurar la implementación interna de Skype Empresarial Server, los usuarios internos de su organización pueden colaborar con otros usuarios internos que tengan cuentas SIP en los Servicios de dominio de Active Directory (AD DS). La colaboración puede incluir el envío y recepción de mensajes instantáneos, y la actualización del estado de presencia y la participación en conferencias (también denominadas "reuniones"). Puede habilitar y configurar el acceso de usuarios externos para controlar si los usuarios externos admitidos pueden colaborar con usuarios internos de Skype Empresarial Server. Los usuarios externos pueden incluir usuarios remotos de la implementación, usuarios federados (incluidos los usuarios admitidos de proveedores de servicios de mensajería instantánea pública) y participantes anónimos en conferencias.

Si la implementación incluía la instalación de un servidor perimetral de Skype Empresarial Server o un grupo de servidores perimetrales, el ámbito de los posibles tipos de comunicación se expande en gran medida con una serie de opciones para el acceso de usuarios externos, la comunicación con miembros de otros dominios federados SIP y proveedores federados SIP. Después de configurar el servidor perimetral o el grupo de servidores perimetrales, habilite los tipos de acceso de usuarios externos que desee proporcionar y configure las directivas para controlar el acceso externo. En Skype Empresarial Server, puede habilitar y configurar directivas y acceso de usuarios externos mediante el Panel de control de Skype Empresarial Server, el Shell de administración de Skype Empresarial [Server](../management-shell.md)o ambos, en función de los requisitos de tarea. 



> [!IMPORTANT]  
> Al diseñar las directivas y la configuración para el acceso de usuario externo, debe comprender la prioridad de las directivas y la manera en que se aplican las directivas. La configuración de directiva de Skype Empresarial Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.


De forma predeterminada, no se configura ninguna directiva para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos y el acceso de usuarios federados, incluso aunque se haya habilitado el acceso de usuarios externos en la organización. Para controlar el acceso de usuarios externos, debe configurar una o más directivas en las que se defina el tipo de acceso de usuario externo que se va a admitir. Algunas de esas directivas son las siguientes:

  - **Directiva global**   La directiva global se crea al implementar los servidores perimetrales. De forma predeterminada, no hay habilitadas opciones de acceso de usuarios externos en la directiva global. Para admitir el acceso de usuarios externos en el nivel global, debe configurar la directiva global para que admita uno o más tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de su organización, pero las directivas de sitio y usuario invalidan la directiva global. Eliminar la directiva global no hará que desaparezca. En lugar de eso, se restablece la configuración predeterminada.

  - **Directiva de sitio**   Puede crear y configurar una o más directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva. Por ejemplo, si activa el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico. De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de dicho sitio, aunque puede asignar una directiva de usuario a un usuario determinado para invalidar dicho parámetro de la directiva de sitio.

  - **Directiva de usuario**   Puede crear y configurar una o más directivas de usuario para limitar la compatibilidad con el acceso de usuarios remotos a usuarios específicos. La configuración de la directiva de usuario invalida la directiva global y la directiva de sitio, pero solo para los usuarios concretos a los que se ha asignado la directiva de usuario. Por ejemplo, si deshabilita el acceso de usuarios remotos en la directiva global y a la directiva de sitio, puede especificar una directiva de usuario para deshabilitar el acceso de usuarios remotos y, a continuación, asignar dicha directiva de usuario a usuarios específicos. Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.

Para determinar qué valores de configuración y qué directivas tiene que crear o editar, consulte los siguientes puntos de decisión:

**¿Desea permitir que los usuarios internos y externos de su dominio puedan colaborar mediante la mensajería instantánea, conferencia web y audio/vídeo?**

Configure las opciones tal y como se detalla en los temas Configurar directivas para controlar la entrada de usuarios remotos [y](external-access-policies/configure-policies-to-control-remote-user-access.md)habilitar o deshabilitar la federación y la conectividad de mensajería [instantánea pública.](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

**¿Desea permitir que los usuarios anónimos asistan y sean invitados a conferencias hospedadas por usuarios en su implementación?**

Configure las opciones como se detalla en el tema Asignar directivas de conferencia para admitir usuarios [anónimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) y crear directivas [de conferencia.](../conferencing/create-policies.md)

**¿Desea permitir a los usuarios que se comuniquen con contactos de dominio federados SIP?**

Configure las opciones como se detalla en los temas [](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)Configurar directivas para controlar el acceso de usuarios federados, [](external-access-policies/configure-policies-to-control-federated-user-access.md)Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública, y Administrar dominios federados SIP para su [organización.](sip-domains/manage-sip-federated-domains-for-your-organization.md)


**Si ha habilitado la comunicación con dominios federados SIP, ¿desea habilitar la detección automática de federación SIP?**

Configure las opciones como se detalla en el tema [Habilitar o deshabilitar la detección de socios de federación.](access-edge/enable-or-disable-discovery-of-federation-partners.md)

**Si ha habilitado la comunicación con dominios de federación SIP, ¿desea habilitar el envío de una declinación de responsabilidades a contactos federados notificándoles que usa el archivado y que las comunicaciones se pueden archivar?**

Configure las opciones como se detalla en el tema Habilitar o deshabilitar el envío de un aviso de declinación de responsabilidades de archivado a [socios federados en](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**¿Desea permitir que los usuarios se comuniquen con proveedores federados SIP que habilitan la comunicación con proveedores públicos?**

Configure las opciones como se detalla en los temas [](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)Configurar directivas para controlar el acceso de usuarios públicos, [](external-access-policies/configure-policies-to-control-public-user-access.md)Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública, y crear o editar proveedores federados SIP [públicos](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**¿Desea permitir que los usuarios se comuniquen con proveedores federados SIP que son proveedores hospedados que ejecutan Microsoft 365 u Office 365 y Skype Empresarial Online?**

Configure las opciones como se [](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) detalla en los temas Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública y Crear o editar proveedores federados [SIP hospedados.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)

**¿Está su implementación configurada en un dominio dividido (también conocido como híbrido), donde algunos usuarios tienen su servidor principal en una implementación local y otros usuarios se configuran con un servidor principal en un entorno en línea?**

Configure las opciones como se [](external-access-policies/configure-policies-to-control-federated-user-access.md)detalla en los temas Configurar directivas para controlar el acceso de usuarios federados, Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea [pública,](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)y crear o editar proveedores federados [SIP hospedados.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)


Puede configurar parámetros de acceso de usuarios externos, incluidas las directivas que desea usar para controlar el acceso de usuarios externos, aunque no haya habilitado el acceso de usuarios externos en su organización. Sin embargo, tanto las directivas como otros parámetros que se configuran solo son efectivos cuando se habilita el acceso de usuarios externos en su organización. Los usuarios externos no pueden comunicarse con usuarios de su organización cuando el acceso de usuarios externos está deshabilitado o no se han configurado directivas de acceso de usuarios externos para admitir dichas comunicaciones.

La implementación perimetral sirve para autenticar los tipos de usuarios externos (excepto los usuarios anónimos, que se autentican mediante el Id. de conferencia y una contraseña que se envía al participante anónimo cuando se crea la conferencia y se invita a los participantes) y controlar el acceso según cómo se haya configurado la compatibilidad perimetral. Para controlar las comunicaciones, puede configurar una o más directivas y otros parámetros que sirvan para definir el modo en que se comunican los usuarios de dentro y fuera de la implementación. Eso incluye la directiva global predeterminada para el acceso de usuarios externos, además de las directivas de sitio y usuario que puede crear y configurar para habilitar uno o más tipos de acceso de usuarios externos para sitios o usuarios específicos.

