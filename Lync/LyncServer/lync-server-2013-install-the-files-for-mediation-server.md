---
title: 'Lync Server 2013: instalar los archivos del servidor de mediación'
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
ms.openlocfilehash: cc7fd5613b39fd17724c9b62152f9d9401fbc072
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498597"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Instalar los archivos del servidor de mediación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-06_

Para completar correctamente este procedimiento, debe iniciar sesión en el servidor, como mínimo, como administrador local y usuario de dominio que pertenezca al menos al grupo RTCUniversalReadOnlyAdmins.

Use los pasos de este tema para ejecutar el Asistente para la implementación de Lync Server 2013 para instalar los archivos del servidor de mediación en un equipo que haya agregado a un grupo de servidores de mediación cuando usó el generador de topologías para definir y publicar el grupo. Al instalar el servidor de mediación de archivos, también se instala y se asigna el certificado que requiere cada equipo en un grupo de servidores de mediación.

En este sitio, si ya ha implementado servidores de mediación combinados en los grupos de servidores front-end o el servidor Standard Edition, puede omitir este tema y continuar con la [configuración de troncos en Lync server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> En este tema se supone que ya se ha definido y publicado un grupo de servidores de mediación independiente, como se describe en <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">definir un servidor de mediación en el generador de topologías en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la documentación de implementación. y que ha comprobado que los equipos del grupo de servidores de mediación cumplen los requisitos previos descritos en <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">requisitos previos de software para telefonía ip empresarial en Lync Server 2013</A> y los <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">requisitos previos de seguridad y configuración para telefonía IP empresarial en Lync Server 2013</A>.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar los archivos de un grupo de servidores de mediación independiente

1.  En el medio de instalación, haga clic con el botón secundario en \<installation media\> ** \\ setup \\ AMD64 \\Setup.exe**y, a continuación, haga clic en **Ejecutar como administrador**.

2.  En la página **Ubicación de instalación** , haga clic en **Aceptar**.

3.  En la página contrato de licencia para el **usuario final** **, haga clic en Acepto y**, a continuación, haga clic en **Aceptar**. (Obligatorio para continuar).

4.  En la página **Asistente para la implementación de Lync server 2010** , haga clic en **instalar o actualizar el sistema Lync Server**.

5.  Junto a **paso 1: instalar almacén de configuración local**, haga clic en **Ejecutar**y siga las instrucciones que aparecen en la pantalla.

6.  En la página **configurar réplica local del almacén de administración central** , acepte la opción predeterminada **recuperar directamente del almacén de administración central**y, a continuación, haga clic en **siguiente**.

7.  En la página **ejecución de comandos** , cuando el estado de la tarea se muestre como **completado**, haga clic en **Finalizar**.

8.  Junto a **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.

9.  En la página **ejecución de comandos** , cuando el estado de la tarea se muestre como **completado**, haga clic en **Finalizar**.

10. Junto a **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado y, por lo tanto, se ejecutará el **paso 3** dos veces: una para emitir el certificado requerido y una vez más para asignarlo.

11. Una vez que el certificado se haya emitido y asignado correctamente, junto al **paso 4: iniciar servicios**, haga clic en **Ejecutar**y siga las instrucciones que aparecen en pantalla.

12. Cuando se haya completado correctamente el **paso 4** , reinicie el servidor e inicie sesión en el servidor como miembro del grupo DomainAdmins.

13. En el equipo en el que ejecuta el panel de control de Lync Server, compruebe en la página de **topología** del panel de control de Lync Server que el estado de servicio del servidor de mediación se muestra como una marca de verificación verde. Si en su lugar aparece una X roja, seleccione el servidor de mediación. En el menú **acción** , haga clic en **iniciar todos los servicios**.

Si agregó más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidores de mediación. Si no necesita instalar archivos para el servidor de mediación para otros equipos, siga los procedimientos que se describen en [Configuring troncos in Lync Server 2013](lync-server-2013-configuring-trunks.md) para establecer la configuración de la conexión troncal entre este grupo de servidores de mediación (o todos los servidores de mediación de un sitio) y su homólogo.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Requisitos de certificado para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

