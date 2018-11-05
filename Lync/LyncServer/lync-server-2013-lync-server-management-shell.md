---
title: Shell de administración de Lync Server
TOCTitle: Shell de administración de Lync Server
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48275504
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Shell de administración de Lync Server

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync Server 2010 incorporó un amplio conjunto de características nuevas y mejoradas con respecto a Microsoft Office Communications Server 2007 R2. Una de las mejoras es la manera de administrar la implementación. Por ejemplo, la nueva interfaz de usuario Panel de control de Lync Server supone un gran cambio en relación con Microsoft Management Console. La otra mejora significativa en la facilidad de administración es haber incluido Windows PowerShell.

Windows PowerShell permite administrar aplicaciones de Microsoft desde la línea de comandos. Incluye un entorno de línea de comandos, comandos específicos de producto y un lenguaje de scripting completo. Windows PowerShell se presentó primero como una versión para descarga para el sistema operativo Windows a finales de 2006 y se incorporó como interfaz de la línea de comandos para facilitar la administración de Microsoft Exchange Server 2007. A partir de ese momento, siguió progresando hasta el punto de haberse incorporado a casi todos los productos de Microsoft Server, el último de los cuales es Microsoft Lync Server 2013. Lync Server 2010 aporta prácticamente 550 cmdlets específicos de producto válidos para administrar casi todos los aspectos de la implementación.

Las secciones siguientes contienen una lista de los cmdlets y sus descripciones. Esta información también se obtiene directamente en la línea de comandos. Únicamente debe escribirse lo siguiente en el símbolo del sistema de Shell de administración de Lync Server:

    Get-Help <cmdlet name> -Full

Por ejemplo, para obtener ayuda en el símbolo del sistema sobre el cmdlet **New-CsVoicePolicy**, escriba lo siguiente:

    Get-Help New-CsVoicePolicy -Full

Aspectos que deben tenerse en cuenta sobre Windows PowerShell en Lync Server 2013:

  - Para ejecutar los cmdlets de Lync Server, abra Shell de administración de Lync Server.
    
    > [!WARNING]  
	> Si abre una ventana de Windows PowerShell en lugar de Shell de administración de Lync Server, de manera predeterminada no podrá ejecutar los cmdlets de Lync Server. Para ejecutar los cmdlets de Lync Server en Windows PowerShell, antes debe escribir lo siguiente en el símbolo del sistema de Windows PowerShell:<br />
    > Import-Module Lync


  - Shell de administración de Lync Server se instala automáticamente en cada servidor front-end Enterprise Edition o servidor Standard Edition de Lync Server.

  - Encontrará información nueva y actualizada, scripts de ejemplo y ayuda de introducción o para profundizar en los cmdlets de Windows PowerShell y Microsoft Lync Server 2013 en el blog de Windows PowerShell de Lync Server[http://go.microsoft.com/fwlink/?linkid=203150\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0xc0a).

