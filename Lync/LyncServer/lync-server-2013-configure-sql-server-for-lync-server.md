---
title: 'Lync Server 2013: configurar SQL Server para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77f6357d38731438555b2c9e3af7ec6a22e9df7c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Configuración de SQL Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-08-12_

En los temas de esta sección se explica cómo implementar y configurar SQL Server para usarlo en una implementación empresarial de Lync Server. Los servidores Standard Edition usan una versión de SQL Server Express de SQL Server combinada que tiene el tamaño adecuado para las cargas de trabajo de un servidor Standard Edition.

El almacén de administración central de Lync Server 2013 retiene datos de usuario para todos los servidores Enterprise Edition de un grupo y está diseñado para ubicarse en un servidor back-end basado en SQL Server. Como repositorio centralizado, el almacén de administración central no se puede instalar en el mismo equipo que cualquier otro rol de Lync Server 2013. El almacén de administración central no puede residir en un servidor Enterprise Edition del grupo de servidores. El almacén de administración central se crea automáticamente cuando se publica la topología por primera vez y se selecciona la creación de las bases de datos. El equipo que designe como servidor back-end debe estar ejecutando el software de base de datos de SQL Server para que la instalación se realice correctamente.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ubicación de los archivos de registro y datos de SQL Server para Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configurar SQL Server en Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Instalación de bases de datos mediante el shell de administración de Lync Server en Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Descripción de los requisitos de Firewall para SQL Server con Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurar la organización en clústeres de SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

