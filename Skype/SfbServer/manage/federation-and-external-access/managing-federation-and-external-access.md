---
title: 'Lync Server 2013: Administración de federación y acceso externo a Skype Empresarial Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Habilite y configure el acceso de usuario externo para controlar si los usuarios externos admitidos pueden colaborar con usuarios internos Skype Empresarial Server.
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676222"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Administración de federación y acceso externo a Skype Empresarial Server

La implementación de un servidor perimetral o de un grupo de servidores perimetrales es el primer paso para la compatibilidad con usuarios externos. Para obtener más información sobre la implementación de servidores perimetrales, consulte [Implementación del servidor perimetral en Skype Empresarial Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Después de instalar y configurar la implementación interna de Skype Empresarial Server, los usuarios internos de la organización pueden colaborar con otros usuarios internos que tengan cuentas SIP en el Servicios de dominio de Active Directory (AD DS). La colaboración puede incluir el envío y recepción de mensajes instantáneos, y la actualización del estado de presencia y la participación en conferencias (también denominadas "reuniones"). Habilite y configure el acceso de usuario externo para controlar si los usuarios externos admitidos pueden colaborar con usuarios internos Skype Empresarial Server. Los usuarios externos pueden incluir usuarios remotos de la implementación, usuarios federados (incluidos los usuarios admitidos de proveedores de servicios de mensajería instantánea pública (MI) y participantes anónimos en conferencias.

Si la implementación incluye un servidor perimetral Skype Empresarial Server o un grupo perimetral, el ámbito de los posibles tipos de comunicación se amplía considerablemente. Hay muchas opciones para el acceso de usuarios externos, la comunicación con miembros de otros dominios federados SIP y proveedores federados SIP. Después de configurar el servidor perimetral o el grupo perimetral, habilite los tipos de acceso de usuario externo y configure las directivas para controlar el acceso externo. En Skype Empresarial Server, habilitará y configurará el acceso de usuarios externos y las directivas mediante el Skype Empresarial Server Panel de control, el [Shell de administración de Skype Empresarial Server](../management-shell.md) o ambos.

> [!IMPORTANT]
> Al diseñar las directivas y la configuración para el acceso de usuario externo, debe comprender la prioridad de las directivas y la manera en que se aplican las directivas. Skype Empresarial Server configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.

De forma predeterminada, ninguna directiva admite el acceso de usuarios externos (incluido el acceso de usuario remoto y el acceso de usuario federado), incluso si ya ha habilitado la compatibilidad con el acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuario externo, debe configurar una o varias directivas. En las directivas siguientes, especifique el tipo de acceso de usuario externo que se admite:

- **Directiva global**: la directiva global se crea al implementar los servidores perimetrales. De forma predeterminada, no hay habilitadas opciones de acceso de usuarios externos en la directiva global. Para admitir el acceso de usuarios externos en el nivel global, configure la directiva global para admitir uno o varios tipos de acceso de usuario externo. La directiva global se aplica a todos los usuarios de su organización, pero las directivas de sitio y usuario invalidan la directiva global. Eliminar la directiva global no hará que desaparezca. En lugar de eso, se restablece la configuración predeterminada.

- **Directiva de sitio**: puede crear y configurar una o varias directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio invalida la directiva global, pero solo para el sitio específico que está cubierto por la directiva de sitio. De forma predeterminada, se aplica una directiva de sitio a todos los usuarios de ese sitio, pero las directivas de usuario para invalidar la configuración de la directiva de sitio.

- **Directiva de usuario**: puede crear y configurar una o varias directivas de usuario para limitar la compatibilidad con el acceso de usuarios remotos a usuarios específicos. La configuración de la directiva de usuario invalida la directiva global y de sitio, pero solo para los usuarios específicos a los que se asigna la directiva. Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.

Para determinar qué valores de configuración y qué directivas tiene que crear o editar, consulte los siguientes puntos de decisión:

**¿Desea permitir que los usuarios internos y externos de su dominio puedan colaborar mediante la mensajería instantánea, conferencia web y audio/vídeo?**

Configure los valores como se detalla en los temas [Configurar directivas para controlar los accesos de usuarios remotos](external-access-policies/configure-policies-to-control-remote-user-access.md) y [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**¿Desea permitir que los usuarios anónimos asistan y sean invitados a conferencias hospedadas por usuarios en su implementación?**

Configure los valores como se detalla en el tema [Asignar directivas de conferencia para admitir usuarios anónimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) y [Crear directivas de conferencia](../conferencing/create-policies.md).

**¿Desea permitir a los usuarios que se comuniquen con contactos de dominio federados SIP?**

Configure las opciones como se detalla en los temas [Configuración de directivas para controlar el acceso de usuarios federados](external-access-policies/configure-policies-to-control-federated-user-access.md), [Habilitación o deshabilitación de la conectividad de federación y mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) y [Administración de dominios federados SIP para su organización](sip-domains/manage-sip-federated-domains-for-your-organization.md).

**Si ha habilitado la comunicación con dominios federados SIP, ¿desea habilitar la detección automática de federación SIP?**

Configure los valores como se detalla en el tema [Habilitar o deshabilitar la detección de asociados de federación](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Si ha habilitado la comunicación con dominios de federación SIP, ¿desea habilitar el envío de una declinación de responsabilidades a contactos federados notificándoles que usa el archivado y que las comunicaciones se pueden archivar?**

Configure los valores como se detalla en el tema [Habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a asociados federados en](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md) .

**¿Desea permitir que los usuarios se comuniquen con proveedores federados SIP que permitan la comunicación con proveedores públicos?**

Configure las opciones como se detalla en los temas [Configuración de directivas para controlar el acceso de usuarios públicos](external-access-policies/configure-policies-to-control-public-user-access.md), [Habilitar o deshabilitar la conectividad de federación y mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) y [Creación o edición de proveedores federados SIP públicos](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)

**¿Desea permitir que los usuarios se comuniquen con proveedores federados SIP que son proveedores hospedados que ejecutan Microsoft 365 o Office 365 y Skype Empresarial Online?**

Configure los valores como se detalla en los temas [Habilitación o deshabilitación de la federación y la conectividad de mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) y [Creación o edición de proveedores federados SIP hospedados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**¿Está su implementación configurada en un dominio dividido (también conocido como híbrido), donde algunos usuarios tienen su servidor principal en una implementación local y otros usuarios se configuran con un servidor principal en un entorno en línea?**

Configure los valores como se detalla en los temas [Configurar directivas para controlar el acceso de usuarios federados](external-access-policies/configure-policies-to-control-federated-user-access.md), [Habilitar o deshabilitar la conectividad de federación y mensajería instantánea pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) y [Crear o editar proveedores federados SIP hospedados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

Puede configurar opciones de acceso de usuario externas incluso si no ha habilitado el acceso de usuario externo para su organización. Sin embargo, tanto las directivas como otros parámetros que se configuran solo son efectivos cuando se habilita el acceso de usuarios externos en su organización. Los usuarios externos no pueden comunicarse con los usuarios cuando el acceso de usuario externo está deshabilitado o si no hay directivas de acceso de usuario externas configuradas para admitirlo.

La implementación perimetral autentica los tipos de usuarios externos y controla el acceso en función de cómo configure la compatibilidad perimetral. La excepción a esta regla son los usuarios anónimos, que se autentican mediante el identificador de conferencia y una clave de acceso que se envía al participante anónimo al crear la conferencia e invitar a los participantes. Para controlar la comunicación, puede configurar una o varias directivas que definan cómo se comunican entre sí los usuarios dentro y fuera de la organización. Las directivas y la configuración incluyen la directiva global predeterminada, las directivas de sitio y las directivas de usuario que puede crear y configurar.
