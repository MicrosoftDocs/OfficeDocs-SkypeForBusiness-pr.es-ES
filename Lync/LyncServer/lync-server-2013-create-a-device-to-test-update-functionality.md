---
title: 'Lync Server 2013: crear un dispositivo para probar la funcionalidad de actualización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b197c4b42542310746568fe351f98c7d991509cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Crear un dispositivo para probar la funcionalidad de actualización en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y, luego, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementarlas en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno de Lync Server) o dentro de un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agregue un dispositivo, aparecerá en la lista de la página **probar dispositivo** del panel de control de Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Para agregar un dispositivo de prueba

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en **probar dispositivo**.

3.  Haga clic en **nuevo**y, a continuación, en **dispositivo de prueba global** o **dispositivo de prueba del sitio**.

4.  Siga uno de estos pasos:
    
      - Si hizo clic en **dispositivo de prueba global**, vaya al siguiente paso.
    
      - Si hizo clic en **dispositivo de prueba de sitio**, seleccione un sitio de la lista de sitios disponibles y, a continuación, haga clic en **Aceptar**.

5.  En **nuevo dispositivo de prueba**, escriba un nombre para el dispositivo en **nombre del dispositivo**.

6.  En **tipo de identificador**, haga clic en **dirección Mac** o en **número de serie**.

7.  En el cuadro **identificador único** , escriba la dirección Mac o el número de serie del dispositivo.

8.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Creación de dispositivos de prueba con cmdlets de Windows PowerShell

Los dispositivos de prueba se pueden crear con Windows PowerShell y el cmdlet New-CsTestDevice. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

Al crear dispositivos de prueba con este cmdlet, debe hacer dos cosas:

  - Especifique MACAddress o SerialNumber como IdentifierType.

  - Incluir el ámbito al especificar la identidad del dispositivo. Para crear un nuevo dispositivo en el ámbito global use una sintaxis similar a la siguiente:
    
        -Identity "global/WindowsPhone"
    
    Para crear un dispositivo de prueba en el ámbito de sitio, use una sintaxis similar a esta:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Para crear un dispositivo de prueba con la dirección MAC

  - Este comando crea un dispositivo de prueba en el ámbito global y usa la dirección MAC como IdentifierType:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Para crear un dispositivo de prueba con el número de serie

  - Este comando crea un nuevo dispositivo de prueba en el ámbito del sitio (para el sitio de Redmond) y usa el número de serie como IdentifierType:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

