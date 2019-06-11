---
title: Requisitos previos de seguridad y configuración para telefonía IP empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d06cdb4c679d1a40eb5c6fa0e8cf837ec8d2e332
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Requisitos previos de seguridad y configuración de telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Compruebe que su infraestructura cumple con los requisitos previos de hardware, configuración de usuario y seguridad específicos de escenarios.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Derechos de administración e infraestructura de certificados

Asegúrese de que su entorno está configurado con los siguientes grupos de usuarios administrativos e infraestructura de certificados para usar durante el proceso de implementación de telefonía IP empresarial.

  - Los administradores que implementen la telefonía IP empresarial deben ser miembros del grupo RTCUniversalServerAdmins.

  - Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:
    
      - **CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.
    
      - **CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Telefonía IP empresarial para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.
    
      - **CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.
    
    <div>
    

    > [!NOTE]
    > La delegación permite que más administradores participen en la implementación de Lync Server sin tener que abrir un acceso innecesario a los recursos.

    
    </div>

  - Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.
    
    <div>
    

    > [!NOTE]
    > Para obtener más información sobre los requisitos de certificado de Lync Server, consulte <A href="lync-server-2013-certificate-infrastructure-requirements.md">requisitos de infraestructura de certificados para Lync server 2013</A> en la documentación de planeación.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Configuración de usuario

Si ha colocado el servidor de mediación con cada grupo de servidores front-end o servidor Standard Edition durante la implementación front end, la configuración de usuario necesaria para la telefonía IP empresarial se configuró automáticamente durante la instalación de los archivos de esos roles de servidor.

Si ha implementado recientemente la carga de trabajo de telefonía IP empresarial en este momento, antes de comenzar el proceso de implementación, designe un número de teléfono principal para cada usuario que tenga previsto habilitar para telefonía IP empresarial. En tanto que administrador, es responsable de asegurarse de que este número sea único. Antes de la implementación, todos los números de teléfono principales deben normalizarse (formateados correctamente) y copiarse en la propiedad del **identificador URI** de cada usuario mediante el panel de control de Lync Server.

<div>


> [!NOTE]
> Para obtener ejemplos de números de teléfono primarios necesarios para la implementación de telefonía IP empresarial, consulte la sección de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync server 2013</A> , sección de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación de planificación.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Pasos siguientes: instalar archivos o configurar conectividad RTC

Después de verificar el software y los requisitos previos del entorno de telefonía IP empresarial, puede usar el siguiente contenido para:

  - Instale el servidor de mediación, como se describe en [instalar los archivos de Media Server en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero solo si desea implementar un servidor o grupo de mediación independiente, ya que los servidores de mediación están instalados como parte de la aplicación de front-end o el estándar Proceso de implementación del servidor de la edición cuando se colocan.

  - También puede empezar a configurar las opciones para enrutar llamadas para usuarios de Enterprise Voice, como se describe en [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

