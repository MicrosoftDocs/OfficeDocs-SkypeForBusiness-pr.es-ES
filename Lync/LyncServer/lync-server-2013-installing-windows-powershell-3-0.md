---
title: 'Lync Server 2013: Instalar Windows PowerShell 3.0'
TOCTitle: Instalar Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48276848
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar Windows PowerShell 3.0 para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para implementar Lync Server 2013 correctamente, necesitará Windows PowerShell 3.0 en todos los equipos que formen parte de la topología de Lync Server.

En los sistemas que ejecutan Windows Server 2012 o Windows Server 2012 R2, no necesita hacer nada aquí y puede ir a la siguiente fase de implementación, porque PowerShell 3.0 está incluido en esos sistemas operativos.

> [!IMPORTANT]  
> En el caso de sistemas que ejecutan Windows Server 2008 R2 SP1, tendrá que instalar PowerShell 3.0 como requisito previo antes de instalar Lync Server 2013 o no funcionará. Para instalar PowerShell 3.0, vea <a href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</a>. Este es un vínculo directo a la página de descarga de PowerShell 3.0, junto con la información relativa a su correcta instalación.



Una vez realizada la instalación, o si solo desea comprobarla y asegurarse de que es correcta antes de continuar con la implementación de Lync Server, la confirmación de que PowerShell 3.0 está en un servidor es bastante sencilla si se hace esto:

1.  En el servidor que desee comprobar, seleccione **Inicio**, **Todos los programas**, **Accesorios**, **Windows PowerShell** y **Windows PowerShell**.

2.  En la consola de Windows PowerShell, escriba el comando siguiente en el símbolo del sistema y presione ENTRAR:
    
        Get-Host | Select-Object Version

3.  Si Windows PowerShell 3.0 está instalado, verá una salida parecida a la siguiente:
    
        Version
        -------
        3.0

