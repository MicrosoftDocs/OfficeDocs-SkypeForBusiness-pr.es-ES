---
title: Eliminar una colección existente de opciones de configuración de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Eliminar una colección existente de opciones de configuración de Lync Phone Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Si ya no desea usar una colección de configuraciones para dispositivos que ejecutan Lync Phone Edition, elimínelo. Si elimina una colección de un sitio, la configuración global se aplicará a los teléfonos de ese sitio. No se puede eliminar la colección global.

<div>


> [!NOTE]
> En lugar de eliminar una colección, es posible que solo desee cambiar algunos de los valores de configuración. Para obtener más información sobre cómo hacerlo, vea <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">crear o modificar una colección de opciones de configuración de Lync Phone Edition en Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Para eliminar una colección de opciones de configuración de Lync Phone Edition

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **configuración de dispositivo** .

4.  En la página **configuración de dispositivo** , haga clic en la colección que desea eliminar, haga clic en el menú **Editar** y, a continuación, haga clic en **eliminar**.
    
    <div>
    

    > [!NOTE]
    > Si elimina la colección global, la configuración solo volverá a la configuración predeterminada. La colección no desaparece.

    
    </div>

5.  En el cuadro de confirmación, haga clic en **Aceptar**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de Lync Phone Edition mediante cmdlets de Windows PowerShell

Puede eliminar la configuración de Lync Phone Edition con Windows PowerShell y el cmdlet **Remove-CsUCConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Para quitar una colección especificada de opciones de configuración de Lync Phone Edition

  - Este comando elimina la configuración de la configuración del teléfono UC aplicada al sitio de Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de Lync Phone Edition aplicadas al ámbito del sitio

  - Este comando elimina todas las opciones de configuración del teléfono UC aplicadas al ámbito de servicio:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Para quitar todas las opciones de configuración de Lync Phone Edition en las que el bloqueo de teléfono está deshabilitado

  - Este comando elimina cualquier colección de parámetros de configuración de teléfono UC en los que se ha deshabilitado el bloqueo de teléfono:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Para obtener más información, consulte [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

