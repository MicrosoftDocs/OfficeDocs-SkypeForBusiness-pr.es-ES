---
title: Modificar la acción predeterminada para clientes no admitidos explícitamente o restringidos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ff08d05c9c8c18b7f81f22b04e2168a14f1a8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Modificar la acción predeterminada para clientes no admitidos explícitamente o restringidos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Además de especificar la versión de clientes que desea admitir en su entorno de Lync Server 2013, también puede especificar una acción predeterminada para clientes que todavía no tienen definida una directiva de versión. Esto le permite restringir las versiones de cliente que se usan en su entorno de Lync Server, lo que puede ayudarle a controlar los costos asociados con la compatibilidad con varias versiones de cliente.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Para modificar la acción predeterminada para clientes que no se admiten explícitamente o que están restringidos

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de versiones de cliente**.

4.  En la página **Configuración de versiones de cliente**, haga doble clic en la configuración **Global** en la lista.

5.  En el cuadro de diálogo **Editar configuración de versiones de cliente**, compruebe que la casilla **Habilitar control de versiones** esté activada y, a continuación, en **Acción predeterminada**, seleccione una de las opciones siguientes:
    
      - **Permitir**   permite que el cliente inicie sesión si la versión de cliente no coincide con ningún filtro de la lista **directivas de versiones de cliente** .
    
      - **Bloquear**   impide que el cliente inicie sesión si la versión de cliente no coincide con ningún filtro de la lista de **directivas de versión de cliente** .
    
      - **Bloquear con dirección URL**   impide que el cliente inicie sesión si la versión de cliente no coincide con ningún filtro de la lista **directivas de versiones de cliente** e incluye un mensaje de error con una dirección URL en la que se puede descargar un cliente más reciente.
    
      - **Permitir con dirección URL**   permite que el cliente inicie sesión si la versión de cliente no coincide con ningún filtro de la lista **directivas de versiones de cliente** e incluye un mensaje de error con una dirección URL en la que se puede descargar un cliente más reciente.

6.  Si selecciona **Bloquear con dirección URL**, escriba en el cuadro **URL** la dirección URL de descarga del cliente que debe incluirse en el mensaje de error.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Para deshabilitar el control de versiones de cliente

  - Para deshabilitar el control de versiones para permitir que todos los clientes inicien sesión independientemente de la versión de cliente, desactive la casilla **Habilitar control de versiones** y haga clic en **Confirmar**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Modificación de la acción predeterminada mediante cmdlets de Windows PowerShell

La acción predeterminada que se realizará cuando los usuarios intenten iniciar sesión mediante clientes que no son explícitamente compatibles o restringidos por una directiva de versión de cliente se pueden administrar mediante la interfaz de línea de comandos de Windows PowerShell y el cmdlet **set-CsClientVersionPolicy** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Para configurar la acción predeterminada para bloquear el acceso

  - El siguiente comando establece la acción predeterminada Bloquear para el sitio Redmond. Esto bloqueará el registro de aquellos clientes para los que no exista ninguna regla de configuración de la versión de cliente.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Para configurar la acción predeterminada para permitir el acceso

  - En este ejemplo, la acción predeterminada para el sitio Redmond se establece en Permitir. Esto permitirá el registro de aquellos clientes para los que no exista ninguna regla de configuración de la versión de cliente.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

