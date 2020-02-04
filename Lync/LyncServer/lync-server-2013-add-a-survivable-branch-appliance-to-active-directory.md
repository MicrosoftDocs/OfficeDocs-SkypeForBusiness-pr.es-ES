---
title: 'Lync Server 2013: Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory'
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
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-23_

Si tiene previsto implementar un dispositivo de sucursal que sea reviviente, debe agregar la aplicación de la rama que es reviviente a los servicios de dominio de Active Directory. Realice este procedimiento en el sitio central.

<div>


> [!IMPORTANT]  
> Realice este procedimiento solo si está implementando un dispositivo de sucursal con la supervivencia. No lo lleve a cabo si está implementando un servidor de sucursal con la supervivencia.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Para agregar un dispositivo de rama con la que los servicios de dominio de Active Directory son supervivientes

1.  Inicie sesión en un servidor miembro como miembro del grupo administradores de la empresa.

2.  Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **usuarios y equipos de Active**Directory.

3.  En el menú **acciones** , haga clic en **nuevo** y, a continuación, en **equipo**.

4.  En el cuadro de diálogo **nuevo objeto-equipo** , escriba un nombre para el objeto de equipo de la aplicación de sucursal que sea sobreviviente (por ejemplo, BranchOffice1) y, a continuación, haga clic en **cambiar**.

5.  En el cuadro de diálogo **Seleccionar usuario o grupo** , agregue el grupo RTCUniversalSBATechnicians y haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Un miembro del grupo RTCUniversalSBATechnicians en el sitio de la sucursal agregará este dispositivo al dominio más adelante.

    
    </div>

6.  Haga clic en **Aceptar** para guardar el objeto de equipo de la aplicación de sucursal superviviente.

7.  Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **ADSI Edit**.

8.  En el editor **ADSI**, haga clic con el botón secundario en el objeto de equipo que creó en los pasos anteriores y, a continuación, haga clic en **propiedades**.

9.  En la lista de atributos, haga clic en **ServicePrincipalName**y, a continuación, en **Editar**.

10. En el **campo valor para agregar** ,\<escriba FQDN\> /SBA de SBA \<donde el\> FQDN de SBA es el nombre de dominio completo (FQDN) de su equipo de sucursal con la supervivencia. Por ejemplo, escriba **host/BranchOffice1. contoso. com**.

11. Haga clic en **Aceptar** para guardar la configuración del atributo **ServicePrincipalName** y, a continuación, haga clic en **Aceptar** para guardar las propiedades del objeto de equipo.

12. En **usuarios y equipos de Active**Directory, haga clic con el botón secundario en **usuarios**, seleccione **nuevo**y, a continuación, haga clic en **usuario**.

13. Escriba información en el Asistente para crear una cuenta de usuario de dominio para un técnico de la aplicación de rama superviviente.

14. En **usuarios y equipos de Active**Directory, haga clic en **usuarios**, haga clic con el botón derecho en el objeto de usuario y, después, haga clic en **Agregar a un grupo**.

15. En **Escriba los nombres de objeto que desea seleccionar**, escriba **RTCUniversalSBATechnicians**y, a continuación, haga clic en **Aceptar**.

16. Repita los pasos 12-15 para cada técnico del sitio de la sucursal.

**Siguiente paso**: [Agregar sitios de sucursales a la topología de Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

