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
ms.openlocfilehash: 91bbaf491abbf40b8cdc3f272ee2b47599c09d3b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Buscar usuarios de Lync Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-14_

Puede usar los resultados de una consulta de búsqueda para configurar usuarios para Lync Server 2013. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.

Puede buscar usuarios con el panel de control de Lync Server o el complemento de usuarios y equipos de Active Directory. El siguiente procedimiento describe cómo usar el panel de control de Lync Server para buscar usuarios.

<div>


> [!NOTE]  
> En un entorno con tipología de bosque central, los resultados de una búsqueda a veces no son muy precisos cuando se busca a un usuario por su dirección de correo electrónico. En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, sip:name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial, o usar el cmdlet <STRONG>Get-CSUser</STRONG>.



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>Para buscar uno o más usuarios

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee buscar y después haga clic en **Buscar**.

5.  (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en la flecha para expandir de la esquina superior derecha de la pantalla que hay sobre **Resultados de la búsqueda** y después haga clic en **Agregar filtro**.
    
    2.  Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista **Igual a**, haga clic en **Igual a** o **No igual a**.
    
    4.  En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados y después haga clic en **Buscar**.

6.  Los resultados de búsqueda aparecerán en el cuadro **Resultados de búsqueda**. Puede seleccionar uno, varios o todos los usuarios de la lista y realizar tareas de configuración en los usuarios seleccionados.

</div>

<div>

## <a name="see-also"></a>Vea también


[Visualización de la información sobre las cuentas de usuario habilitadas para Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Habilitación y deshabilitación de usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

