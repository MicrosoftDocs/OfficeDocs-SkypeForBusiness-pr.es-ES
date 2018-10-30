---
title: Creación de un dispositivo para probar la funcionalidad de las actualizaciones
TOCTitle: Creación de un dispositivo para probar la funcionalidad de las actualizaciones
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48276698
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación de un dispositivo para probar la funcionalidad de las actualizaciones

 

_**Última modificación del tema:** 2013-02-23_

Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y luego usar este dispositivo para comprobar las funciones de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Pruebe un dispositivo de forma global (en todo el entorno de Lync Server) o en un sitio único. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agrega un dispositivo, aparece en la lista de la página **Dispositivo de prueba** de Panel de control de Lync Server.

## Para agregar un dispositivo de prueba

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Clientes** y luego en **Dispositivo de prueba**.

3.  Haga clic en **Nuevo** y después en **Dispositivo de prueba global** o en **Dispositivo de prueba de sitio**.

4.  Siga uno de estos procedimientos:
    
      - Si hizo clic en **Dispositivo de prueba global**, vaya al paso siguiente.
    
      - Si hizo clic en **Dispositivo de prueba de sitio**, seleccione un sitio en la lista de sitios disponibles y luego haga clic en **Aceptar**.

5.  En **Dispositivo de prueba nuevo**, especifique un nombre para el dispositivo en **Nombre de dispositivo**.

6.  En **Tipo de identificador**, haga clic en **Dirección MAC** o en **Número de serie**.

7.  En el cuadro **Identificador único**, escriba la dirección MAC o número de serie del dispositivo.

8.  Haga clic en **Confirmar**.

## Crear dispositivos de prueba mediante cmdlets de Windows PowerShell

Los dispositivos de prueba se pueden crear con Windows PowerShell y el cmdlet New-CsTestDevice. Este cmdlet se ejecuta desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

Cuando cree dispositivos de prueba con este cmdlet, haga dos cosas:

  - Especifique el valor de MACAddress o de SerialNumber como IdentifierType.

  - Incluya el ámbito cuando especifique la identidad del dispositivo. Para crear un dispositivo nuevo en el ámbito global use una sintaxis similar a la siguiente:
    
        -Identity "global/WindowsPhone"
    
    Para crear un dispositivo de prueba en el ámbito del sitio, use una sintaxis similar a la siguiente:
    
        -Identity "site:Redmond/WindowsPhone"

## Para crear un dispositivo de prueba mediante una dirección MAC

  - Este comando crea un dispositivo de prueba en el ámbito global y usa la dirección MAC como IdentifierType:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

## Para crear un dispositivo de prueba mediante un número de serie

  - Este comando crea un dispositivo de prueba nuevo en el ámbito de sitio (para el sitio de Redmond) y usa el número de serie como IdentifierType:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

Para más información, vea el tema de ayuda del cmdlet [New-CsTestDevice](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTestDevice).

