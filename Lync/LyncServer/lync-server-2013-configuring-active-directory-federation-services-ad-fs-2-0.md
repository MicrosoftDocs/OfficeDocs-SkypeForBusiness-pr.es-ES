---
title: 'Lync Server 2013: configuración de servicios de Federación de Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a88fb9db7109bdd2a2938f8f9624b4fd0f369fd9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Configuración de servicios de Federación de Active Directory (AD FS 2,0) para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

En la siguiente sección se describe cómo configurar los servicios de federación de Active Directory (AD FS 2.0) para admitir autenticación multifactor. Para obtener más información sobre cómo instalar 2,0 de AD FS, consulte instrucciones paso a paso de AD FS 2,0 y guías de [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)procedimientos en.

<div class="">


> [!NOTE]  
> Al instalar AD FS 2.0, no use Windows Server Manager para agregar el rol de los servicios de federación de Active Directory. En su lugar, descargue e instale el paquete de servicios de Federación de Active <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>Directory 2,0 RTW en.



</div>

<div>


**Para configurar AD FS para la autenticación en dos fases**

1.  Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.

2.  Inicie Windows PowerShell.

3.  Desde la línea de comandos de Windows PowerShell, ejecute el siguiente comando:
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Establezca una asociación con cada servidor de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: Director de 2013 julio de 2017, grupo empresarial y servidor Standard Edition que se habilitará para la autenticación pasiva ejecutando el siguiente comando, sustituyendo el nombre del servidor específico de su implementación:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Desde el menú Herramientas administrativas, inicie la consola de administración de AD FS 2.0.

6.  Expanda **relaciones** \> de confianza **confianzas**de usuario de confianza.

7.  Compruebe que se ha creado una nueva confianza para su Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013: Grupo de servidores Enterprise o servidor Standard Edition de julio de 2013.

8.  Cree y asigne una regla de autorización de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Cree y asigne una regla de transformación de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. Desde la consola de administración de AD FS 2.0, haga clic con el botón secundario en la relación de confianza para el usuario autenticado y seleccione **Editar reglas de notificaciones**.

11. Seleccione la pestaña **Reglas de autorización de emisión** y compruebe que la nueva regla de autorización se haya creado correctamente.

12. Seleccione la pestaña **Reglas de transformación de emisión** y compruebe que la nueva regla de transformación se haya creado correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

