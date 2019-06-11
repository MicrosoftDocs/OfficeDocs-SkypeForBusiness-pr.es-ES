---
title: Modificar la acción predeterminada de los clientes que no se admiten o restringen explícitamente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Modificar la acción predeterminada de los clientes que no se admiten explícitamente o restringen en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Además de especificar la versión de clientes que desea admitir en su entorno de Lync Server 2013, también puede especificar una acción predeterminada para los clientes que aún no tienen definida una directiva de versión. Esto le permite restringir las versiones de cliente que se usan en su entorno de Lync Server, lo que puede ayudarle a controlar los costos asociados con la compatibilidad de varias versiones de cliente.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Para modificar la acción predeterminada para los clientes que no son explícitamente compatibles o restringidos

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, después, en **configuración de versión de cliente**.

4.  En la página Configuración de la **versión del cliente** , haga doble clic en la configuración **global** de la lista.

5.  En el cuadro de diálogo **Editar configuración** de la versión del cliente, compruebe que la casilla de verificación **Habilitar control de versiones** está seleccionada y, a continuación, en **acción predeterminada**, seleccione una de las opciones siguientes:
    
      - **Permitir**   permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro de la lista de **directivas de versión del cliente** .
    
      - **Bloquear**   impide que el cliente inicie sesión si la versión del cliente no coincide con ningún filtro de la lista de **directivas de versión de cliente** .
    
      - **Bloquear con dirección URL**   impide que el cliente inicie sesión si la versión del cliente no coincide con ningún filtro de la lista de **directivas de versión del cliente** e incluye un mensaje de error que contenga una dirección URL donde se pueda descargar un cliente más reciente.
    
      - **Permitir con URL**   permite al cliente iniciar sesión si la versión del cliente no coincide con ninguno de los filtros de la lista de **directivas de versión del cliente** e incluye un mensaje de error que contenga una dirección URL donde se pueda descargar un cliente más reciente.

6.  Si seleccionó **bloquear con URL**, escriba la dirección URL de descarga del cliente que desea incluir en el mensaje de error en el cuadro **dirección URL** .

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Para deshabilitar el control de versiones del cliente

  - Para deshabilitar el control de versiones y permitir que todos los clientes inicien sesión independientemente de la versión del cliente, desactive la casilla **Habilitar control de versiones** y, a continuación, haga clic en **confirmar**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Modificar la acción predeterminada mediante cmdlets de Windows PowerShell

La acción predeterminada que hay que realizar cuando los usuarios intentan iniciar sesión con clientes que no son explícitamente compatibles o restringidos por una directiva de versión de cliente se pueden administrar mediante la interfaz de línea de comandos de Windows PowerShell y el cmdlet **set-CsClientVersionPolicy** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Para configurar la acción predeterminada para bloquear el acceso

  - El siguiente comando establece la acción predeterminada para el bloque de sitio de Redmond. Esto bloqueará el registro de cualquier cliente para el que no exista ninguna regla de configuración de versión de cliente.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Para configurar la acción predeterminada para permitir el acceso

  - En este ejemplo, la acción predeterminada para el sitio de Redmond es permitir. Esto permitirá el registro de cualquier cliente para el que no exista ninguna regla de configuración de la versión de cliente.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

