---
title: 'Lync Server 2013: instalar los archivos para el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c84d5fc2c863e0e56af275a4bee084652742eeac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Instalar los archivos de Media Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-06_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio que pertenezca, como mínimo, al grupo RTCUniversalReadOnlyAdmins.

Siga los pasos que se indican en este tema para ejecutar el Asistente para la implementación de Lync Server 2013 para instalar los archivos del servidor de mediación en un equipo que haya agregado a un grupo de servidores de mediación cuando usó el generador de topología para definir y publicar el grupo. Al instalar el servidor de mediación de archivos, también puede instalar y asignar el certificado requerido por cada equipo de un grupo de servidores de mediación.

En este sitio, si ya ha implementado servidores de mediación colocados en las agrupaciones front-end o en el servidor Standard Edition, puede omitir este tema y, en su lugar, seguir [configurando troncos en Lync server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> En este tema se supone que ya ha definido y publicado un grupo de servidores de mediación independiente, tal como se describe en <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">definir un servidor de mediación en el generador de topología en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la documentación de implementación. y si ha verificado que los equipos del grupo de servidores de mediación cumplen los requisitos previos descritos en los <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">requisitos de software de telefonía ip empresarial de Lync Server 2013</A> y los <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">requisitos previos de seguridad y configuración de Enterprise Voz en Lync Server 2013</A>.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar los archivos de un grupo de servidores de mediación independiente

1.  En el medio de instalación, haga clic \<con el\>botón derecho en instalación de medios**\\de instalación\\AMD64\\Setup. exe**y luego haga clic en **Ejecutar como administrador**.

2.  En la página **Ubicación de la instalación**, haga clic en **Aceptar**.

3.  En la página **Contrato de licencia para el usuario final**, seleccione **Aceptar** y, a continuación, haga clic en **Aceptar**. (Es necesario para poder continuar).

4.  En la página **Asistente para la implementación de Lync server 2010** , haga clic en **instalar o actualizar el sistema de Lync Server**.

5.  Junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.

6.  En la página **Configurar réplica local del almacén de administración central**, acepte la opción predeterminada **Recuperar directamente de almacén de administración central**; a continuación, haga clic en **Siguiente**.

7.  En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.

8.  Junto al **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.

9.  En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.

10. Junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado, por eso el **Paso 3** se debe ejecutar dos veces: una para emitir el certificado requerido y una más para asignarlo.

11. Una vez se ha emitido y asignado correctamente el certificado, junto a **Paso 4: Iniciar servicios**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.

12. Tras completar correctamente el **Paso 4**, reinicie el servidor e inicie sesión en él como miembro del grupo DomainAdmins.

13. En el equipo en el que esté ejecutando el panel de control de Lync Server, compruebe en la página **topología** del panel de control de Lync Server que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde. Si en lugar de ello aparece una X de color rojo, seleccione el servidor de mediación. En el menú **Acción**, haga clic en **Iniciar todos los servicios**.

Si ha agregado más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidores de mediación. Si no necesita instalar archivos para el servidor de mediación para ningún otro equipo, siga los procedimientos de [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) para configurar las opciones de la conexión troncal entre este grupo de servidores de mediación (o todos los servidores de mediación de un sitio) y su par.

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

