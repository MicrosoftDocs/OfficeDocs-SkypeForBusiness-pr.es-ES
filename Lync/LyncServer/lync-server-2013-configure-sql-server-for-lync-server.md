---
title: 'Lync Server 2013: Configurar SQL Server para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0154b468540873f9b8ae6796f30336327809d394
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Configurar SQL Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-08-12_

En los temas de esta sección se explica cómo implementar y configurar SQL Server para usarlo en una implementación empresarial de Lync Server. Los servidores Standard Edition usan una versión de SQL Server Express de SQL Server, que tiene el tamaño adecuado para las cargas de trabajo de un servidor Standard Edition.

El almacén de administración central de Lync Server 2013 contiene los datos de usuario de todos los servidores Enterprise Edition de un grupo de servidores y se ha diseñado para ubicarse en un servidor back-end basado en SQL Server. Como repositorio centralizado, el almacén central de administración no se puede instalar en el mismo equipo que cualquier otro rol de Lync Server 2013. El almacén central de administración no puede residir en un servidor Enterprise Edition del grupo. El almacén de administración central se crea automáticamente cuando se publica la topología por primera vez y se selecciona para crear las bases de datos. El equipo que designe como servidor back-end ya debe estar ejecutando el software de base de datos de SQL Server para que la instalación se realice correctamente.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ubicación de datos y de archivos de registro de SQL Server para Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configurar SQL Server en Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Instalación de la base de datos con el Shell de administración de Lync Server en Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Descripción de los requisitos de firewall para SQL Server con Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurar clústeres de SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

