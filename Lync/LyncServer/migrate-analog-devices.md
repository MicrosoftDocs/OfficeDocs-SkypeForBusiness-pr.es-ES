---
title: Migrar dispositivos analógicos
TOCTitle: Migrar dispositivos analógicos
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49889529
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar dispositivos analógicos

 

_**Última modificación del tema:** 2012-10-16_

Lync Server ofrece compatibilidad con dispositivos analógicos, concretamente con teléfonos de audio y máquinas de fax. Puede configurar las puertas de enlace preparadas para el uso de dispositivos analógicos en un entorno de Lync Server. Tras migrar de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados a los dispositivos analógicos. Use el Shell de administración de Lync Server para recuperar primero todos los objetos de contacto asociados a los dispositivos analógicos de Lync Server 2010 y luego mueva esos objetos al grupo de servidores Lync Server 2013.

## Para migrar dispositivos analógicos

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  En la línea de comandos, escriba lo siguiente:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Compruebe que todos los objetos de contacto se hayan movido al grupo de servidores Lync Server 2013. En la línea de comandos, escriba lo siguiente:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Compruebe que todos los objetos de contacto estén asociados ahora al grupo de servidores Lync Server 2013.

