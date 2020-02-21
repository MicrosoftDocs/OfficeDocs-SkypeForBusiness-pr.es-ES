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
ms.openlocfilehash: 67712f981d8061b8dd3c90de812092e01dc5d1b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Crear un dispositivo para probar la funcionalidad de actualización en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y luego usar este dispositivo para comprobar las funciones de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno de Lync Server) o dentro de un único sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando se agrega un dispositivo, aparece en la lista de la página **probar dispositivo** del panel de control de Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Para agregar un dispositivo de prueba

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Clientes** y luego en **Dispositivo de prueba**.

3.  Haga clic en **Nuevo** y después en **Dispositivo de prueba global** o en **Dispositivo de prueba de sitio**.

4.  Siga uno de estos procedimientos:
    
      - Si hizo clic en **Dispositivo de prueba global**, vaya al paso siguiente.
    
      - Si hizo clic en **Dispositivo de prueba de sitio**, seleccione un sitio en la lista de sitios disponibles y luego haga clic en **Aceptar**.

5.  En **Dispositivo de prueba nuevo**, especifique un nombre para el dispositivo en **Nombre de dispositivo**.

6.  En **Tipo de identificador**, haga clic en **Dirección MAC** o en **Número de serie**.

7.  En el cuadro **Identificador único**, escriba la dirección MAC o número de serie del dispositivo.

8.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Creación de dispositivos de prueba mediante cmdlets de Windows PowerShell

Los dispositivos de prueba se pueden crear con Windows PowerShell y el cmdlet New-CsTestDevice. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

Cuando cree dispositivos de prueba con este cmdlet, haga dos cosas:

  - Especifique el valor de MACAddress o de SerialNumber como IdentifierType.

  - Incluya el ámbito cuando especifique la identidad del dispositivo. Para crear un dispositivo nuevo en el ámbito global use una sintaxis similar a la siguiente:
    
        -Identity "global/WindowsPhone"
    
    Para crear un dispositivo de prueba en el ámbito del sitio, use una sintaxis similar a la siguiente:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Para crear un dispositivo de prueba con la dirección MAC

  - Este comando crea un dispositivo de prueba en el ámbito global y usa la dirección MAC como IdentifierType:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Para crear un dispositivo de prueba mediante el número de serie

  - Este comando crea un dispositivo de prueba nuevo en el ámbito de sitio (para el sitio de Redmond) y usa el número de serie como IdentifierType:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

