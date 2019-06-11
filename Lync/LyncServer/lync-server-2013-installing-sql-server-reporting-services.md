---
title: 'Lync Server 2013: instalar SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6707cafc3a08123bd2189639704741681eb9cdd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Instalar SQL Server Reporting Services en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Si tiene previsto usar los informes de supervisión de Microsoft Lync Server 2013 (consulte la siguiente sección de esta documentación para obtener más información) primero debe instalar SQL Server Reporting Services. Reporting Services puede instalarse al mismo tiempo que instala Microsoft SQL Server o en cualquier momento después de instalar SQL Server. Esto puede realizarse al mismo tiempo que instala Microsoft SQL Server o después de instalar SQL Server. Si no ha instalado SQL Server, siga las instrucciones suministradas anteriormente en esta documentación. Al instalar SQL Server, asegúrese de que selecciona Reporting Services en la página Selección de características, ya que de este modo se instalará SQL Server Reporting Services.

Si ya ha instalado SQL Server pero no ha instalado SQL Server Reporting Services, puede agregar esa característica siguiendo el conjunto adecuado de instrucciones para SQL Server 2008 R2 o SQL Server 2012, según corresponda.

Siga los pasos que se indican a continuación para comprobar que Reporting Services se ha instalado correctamente:

1.  Si está ejecutando Microsoft SQL Server 2008 R2, haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft SQL Server 2008 R2**, **herramientas de configuración**y, a continuación, haga clic en **Administrador de configuración**de Reporting Services.
    
    Si está ejecutando Microsoft SQL Server 2012, haga clic en **Inicio**, haga clic en **todos los programas**, en **Microsoft SQL Server 2012**, en **herramientas de configuración**y, por último, en **Administrador de configuración**de Reporting Services.

2.  En el cuadro de diálogo **conexión de configuración** de Reporting Services, compruebe que el nombre del servidor aparece en el cuadro **nombre del servidor** y que el nombre de la instancia de SQL Server que almacena los datos de supervisión aparece en el servidor de **informes **Cuadro de instancia. Haga clic en **conectar**.

En el administrador de configuración del servicio de informes, el panel estado del servidor de informes debe mostrar que SQL Server Reporting Services se ha instalado y que los servicios de creación de informes se están ejecutando: el estado del servidor de informes debe mostrarse como **iniciado** y el botón **Inicio** debe estar atenuado y no disponible. Si el servicio de informes no se está ejecutando, haga clic en **iniciar** para iniciar el servicio.

Si no aparece ninguna base de datos junto a la etiqueta nombre de base de datos del servidor de informes, haga lo siguiente:

1.  En el administrador de configuración de Reporting Services, haga clic en **base de datos**.

2.  En el panel base de datos del servidor de informes, haga clic en **Cambiar base de datos**.

3.  En el Asistente para la configuración de base de datos del servidor de informes, en el panel de acciones, seleccione **crear una nueva base de datos del servidor de informes** y haga clic en **siguiente**.

4.  En el Asistente para la configuración de base de datos del servidor de informes, en el panel servidor de base de datos, compruebe que la información que aparece en los cuadros **nombre del servidor**, **tipo de autenticación**y nombre de **usuario** es correcta. Haga clic en **probar conexión** para comprobar que se puede establecer una conexión con el servidor de base de datos y, a continuación, haga clic en **siguiente**.

5.  En el Asistente para la configuración de base de datos del servidor de informes, en el panel base de datos, acepte los valores predeterminados para nombre de la **base de datos**, **idioma**y **servidor de informes** y haga clic en **siguiente**.

6.  En el Asistente para la configuración de base de datos del servidor de informes, en el panel credenciales, compruebe que la información correcta aparece en la lista desplegable **tipo de autenticación** y los cuadros **nombre de usuario** y **contraseña** y, a continuación, haga clic en **siguiente**.

7.  En el Asistente para la configuración de base de datos del servidor de informes, en el panel Resumen, haga clic en **siguiente**.

8.  En el Asistente para la configuración de base de datos del servidor de informes, en el panel progreso y finalizar, haga clic en **Finalizar**.

Para comprobar que las direcciones URL de Reporting Services se han configurado, haga clic en **URL de servicio Web**. Debería ver una o más direcciones URL en las **direcciones URL del servicio Web del servidor de informes**de encabezado. Haga clic en cada una de estas direcciones URL para comprobar que puede ponerse en contacto con la Página principal de la instalación local de SQL Server Reporting Services.

</div>

<span> </span>

</div>

</div>

</div>

