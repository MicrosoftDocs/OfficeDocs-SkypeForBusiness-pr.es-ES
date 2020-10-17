---
title: Requisitos previos de seguridad y configuración para telefonía IP empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8f0f3dd113b10a01f18a0542561de946d4acd0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510477"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Requisitos previos de seguridad y configuración para telefonía IP empresarial en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Compruebe que la infraestructura cumple con los siguientes requisitos previos de seguridad, configuración de usuario y hardware específico del escenario.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Derechos administrativos e infraestructura de certificados

Asegúrese de que el entorno está configurado de forma que se usan los siguientes grupos de usuarios administrativos e infraestructura de certificados durante el proceso de implementación de Enterprise Voice.

  - Los administradores que implementen Enterprise Voice deben ser miembros del grupo RTCUniversalServerAdmins.

  - Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:
    
      - **CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.
    
      - **CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Enterprise Voice para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.
    
      - **CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.
    
    <div>
    

    > [!NOTE]
    > La delegación permite que más administradores participen en su implementación de Lync Server sin tener que abrir un acceso innecesario a los recursos.

    
    </div>

  - Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.
    
    <div>
    

    > [!NOTE]
    > Para obtener más información sobre los requisitos de certificado en Lync Server, vea <A href="lync-server-2013-certificate-infrastructure-requirements.md">requisitos de infraestructura de certificados para Lync server 2013</A> en la documentación referente a la planeación.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Configuración de usuario

Si ha combinado el servidor de mediación con cada grupo de servidores front-end o servidor Standard Edition durante la implementación front-end, la configuración de usuario necesaria para la telefonía IP empresarial se configuró automáticamente durante la instalación de los archivos de dichos roles de servidor.

En caso de que esté implementando la carga de trabajo de Enterprise Voice por primera vez, antes de iniciar el proceso, designe un número de teléfono principal por cada usuario para el que tenga previsto habilitar Enterprise Voice. En tanto que administrador, es responsable de asegurarse de que este número sea único. Antes de la implementación, todos los números de teléfono principales deben normalizarse (formateados correctamente) y copiarse en la propiedad de **URI de línea** de cada usuario mediante el panel de control de Lync Server.

<div>


> [!NOTE]
> Para obtener ejemplos de números de teléfono principales necesarios para la implementación de telefonía IP empresarial, consulte la sección <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync server 2013</A> de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación referente a la planeación.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Pasos siguientes: Instalar archivos o configurar la conectividad RTC

Una vez confirmados los requisitos previos de software y entorno para Enterprise Voice, puede usar el siguiente contenido para:

  - Instale el servidor de mediación, tal y como se describe en [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero solo si desea implementar un servidor o grupo de servidores de mediación independiente, ya que los servidores de mediación se instalan como parte del grupo de servidores front-end o del proceso de implementación de servidor Standard Edition al combinarse.

  - O bien, comience a configurar las opciones para enrutar las llamadas de los usuarios de Enterprise Voice, tal como se describe en [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

