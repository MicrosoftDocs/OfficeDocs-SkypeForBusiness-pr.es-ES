---
title: 'Lync Server 2013: agregar una aplicación de sucursal con funciones de supervivencia a Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da38ead0e1d27ef1024d8aac2ea030d2815e6cad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-23_

Si tiene previsto implementar una aplicación de sucursal con funciones de supervivencia, debe agregar la aplicación de sucursal con funciones de supervivencia a los servicios de dominio de Active Directory. Realice este procedimiento en el sitio central.

<div>


> [!IMPORTANT]  
> Realice este procedimiento únicamente si va a implementar una aplicación de sucursal con funciones de supervivencia. No lo haga si va a implementar un servidor de sucursal con funciones de supervivencia.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Para agregar una aplicación de sucursal con funciones de supervivencia a los Servicios de dominio de Active Directory

1.  Inicie sesión en un servidor miembro como miembro del grupo Administradores de organización.

2.  Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Usuarios y equipos de Active Directory**.

3.  En el menú **Acciones**, haga clic en **Nuevo** y, a continuación, en **Equipo**.

4.  En el cuadro de diálogo **nuevo objeto-equipo** , escriba un nombre para el objeto de equipo de aplicación de sucursal con funciones de supervivencia (por ejemplo, BranchOffice1) y, a continuación, haga clic en **cambiar**.

5.  En el cuadro de diálogo **Seleccionar usuario o grupo**, agregue el grupo RTCUniversalSBATechnicians y haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Más adelante, un miembro del grupo RTCUniversalSBATechnicians del sitio de sucursal agregará este dispositivo al dominio.

    
    </div>

6.  Haga clic en **Aceptar** para guardar el objeto de equipo de aplicación de sucursal con funciones de supervivencia.

7.  Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Editor ADSI**.

8.  En el **Editor ADSI**, haga clic con el botón secundario en el objeto de equipo que creó en los pasos anteriores y, a continuación, haga clic en **Propiedades**.

9.  En la lista de atributos, haga clic en **servicePrincipalName** y luego en **Editar**.

10. En el **campo valor para agregar** ,\<escriba FQDN\> de host/SBA \<donde el\> FQDN de SBA es el nombre de dominio completo (FQDN) de la aplicación de sucursal con funciones de supervivencia. Por ejemplo, escriba **HOST/BranchOffice1.contoso.com**.

11. Haga clic en **Aceptar** para guardar la configuración de atributo **servicePrincipalName** y, a continuación, en **Aceptar** para guardar las propiedades del objeto de equipo.

12. En **Usuarios y equipos de Active Directory**, haga clic con el botón secundario en **Usuarios**, haga clic en **Nuevo** y, a continuación, en **Usuario**.

13. Escriba información en el Asistente para crear una cuenta de usuario de dominio para un técnico de la aplicación de sucursal con funciones de supervivencia.

14. En **Usuarios y equipos de Active Directory**, haga clic en **Usuarios**, haga clic con el botón secundario en el objeto de equipo y luego haga clic **Agregar a un grupo**.

15. En **Escribir los nombres de objeto para seleccionar**, escriba **RTCUniversalSBATechnicians** y haga clic en **Aceptar**.

16. Repita los pasos 12-15 para cada técnico del sitio de sucursal.

**Siguiente paso**: [Agregar sitios de sucursal a la topología en Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

