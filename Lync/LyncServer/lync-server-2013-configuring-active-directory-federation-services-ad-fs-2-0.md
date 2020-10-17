---
title: 'Lync Server 2013: configuración de los servicios de Federación de Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac26f7ec2be8390ee913c810928cc99c4e20d53c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517657"
---
# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Configuración de los servicios de Federación de Active Directory (AD FS 2,0) para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

En la siguiente sección se describe cómo configurar los servicios de Federación de Active Directory (AD FS 2,0) para que admitan la autenticación multifactor. Para obtener información sobre cómo instalar AD FS 2,0, consulte las guías paso a paso y de procedimientos de AD FS 2,0 en [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374) .

<div class="">


> [!NOTE]  
> Al instalar AD FS 2,0, no use el administrador de servidores de Windows para agregar el rol de los servicios de Federación de Active Directory. En su lugar, descargue e instale el paquete 2,0 RTW de los servicios de Federación de Active Directory en <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A> .



</div>

<div>


**Para configurar AD FS para la autenticación en dos fases**

1.  Inicie sesión en el equipo con AD FS 2,0 con una cuenta de administrador de dominio.

2.  Iniciar Windows PowerShell

3.  Desde la línea de comandos de Windows PowerShell, ejecute el siguiente comando:
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Establezca una asociación con cada Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: Director de julio de 2013, grupo de servidores Enterprise y servidor Standard Edition que se habilitarán para la autenticación pasiva mediante la ejecución del siguiente comando, que reemplaza el nombre del servidor específico de la implementación:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  En el menú Herramientas administrativas, inicie la consola de administración de AD FS 2,0.

6.  Expanda **relaciones de confianza relaciones** de \> **confianza para usuario autenticado**.

7.  Compruebe que se haya creado una nueva confianza para Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: Grupo de servidores Enterprise o servidor Standard Edition de julio de 2013.

8.  Cree y asigne una regla de autorización de emisión para la relación de confianza para usuario autenticado con Windows PowerShell; para ello, ejecute los siguientes comandos:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Cree y asigne una regla de transformación de emisión para la relación de confianza para usuario autenticado con Windows PowerShell; para ello, ejecute los siguientes comandos:
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. Desde la consola de Administración AD FS 2,0, haga clic con el botón secundario en su relación de confianza para usuario autenticado y seleccione **editar reglas de notificación**.

11. Seleccione la pestaña **reglas de autorización de emisión** y compruebe que la nueva regla de autorización se haya creado correctamente.

12. Seleccione la ficha **reglas de transformación de emisión** y compruebe que la nueva regla de transformación se haya creado correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

