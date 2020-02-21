---
title: 'Lync Server 2013: instalar la base de datos del servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 877a9b8519c6c0e8b0c3e4a92d190f5a55d8861e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Instalar la base de datos del servidor Standard Edition para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La configuración de un servidor Standard Edition como el único servidor de la infraestructura que aloja a los usuarios se diferencia de otras instalaciones de servidores en que hay una selección en el Asistente para la **implementación** específica para configurar el servidor inicial.

<div>

## <a name="to-install-a-standard-edition-server"></a>Para instalar un servidor Standard Edition

1.  Inicie sesión en el servidor en el que va a instalar el servidor Standard Edition como administrador local o como equivalente en un dominio.

2.  Si no ha preparado los servicios de dominio de Active Directory, primero realice estos procedimientos. Para obtener más información, consulte [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  En el Asistente para la implementación de Lync Server, haga clic en **preparar el primer servidor Standard Edition**.

4.  En la página **Preparar un solo servidor Standard Edition**, haga clic en **Siguiente**.

5.  En la página **ejecución de comandos** , se instala SQL Server 2012 Express como almacén de administración central. Se crean las reglas de firewall necesarias. Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en  **Finalizar **.
    
    <div>
    

    > [!NOTE]  
    > Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos. Esto se debe a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo.

    
    </div>

6.  En la página del Asistente para la implementación de Lync Server, haga clic en **instalar Topology Builder** si no ha instalado previamente las herramientas administrativas. Para obtener más información, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Confirme que hay marcas de verificación verdes junto a “Preparar Active Directory,” “Preparar el primer servidor Standard Edition” e “Instalar Topology Builder”.

</div>

</div>

<span> </span>

</div>

</div>

</div>

