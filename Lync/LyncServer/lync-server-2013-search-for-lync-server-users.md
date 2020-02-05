---
title: 'Lync Server 2013: Buscar usuarios de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7134afbc86134471e8d536b36fc8e28142a64db2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Buscar usuarios de Lync Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-14_

Puede usar los resultados de una consulta de búsqueda para configurar usuarios para Lync Server 2013. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.

Puede buscar usuarios mediante el panel de control de Lync Server o el complemento usuarios y equipos de Active Directory. En el procedimiento siguiente se describe cómo usar Lync Server panel de control para buscar usuarios.

<div>


> [!NOTE]  
> En un entorno con una topología de bosque central, los resultados de la búsqueda podrían no ser exactos al buscar un usuario por la dirección de correo electrónico del usuario. En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, SIP: Name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial o usar el cmdlet <STRONG>Get-CSUser</STRONG> .



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>Para buscar uno o más usuarios

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta SAM, la dirección SIP o el URI de línea de la cuenta de usuario que desea buscar y, a continuación, haga clic en **Buscar**.

5.  (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en el botón de flecha Expandir situado en la esquina superior derecha de la pantalla, encima de resultados de la **búsqueda**, y haga clic en **Agregar filtro**.
    
    2.  Escriba la propiedad de usuario escribiéndola o haciendo clic en la flecha de la lista desplegable para seleccionar una propiedad de usuario.
    
    3.  En la lista **igual a** , haga clic en **igual a** o **no es igual a**.
    
    4.  En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados de la búsqueda y, a continuación, haga clic en **Buscar**.

6.  Los resultados de la búsqueda aparecen en resultados de la **búsqueda**. Puede seleccionar cualquiera de los usuarios de la lista o todos ellos y realizar tareas de configuración en los usuarios que seleccione.

</div>

<div>

## <a name="see-also"></a>Vea también


[Ver información sobre las cuentas de usuario habilitadas para Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

