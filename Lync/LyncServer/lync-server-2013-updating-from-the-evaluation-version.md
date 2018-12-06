---
title: Actualización de la versión de evaluación de Lync Server 2013
TOCTitle: Actualización de la versión de evaluación de Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48275458
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Actualización de la versión de evaluación de Lync Server 2013

 

_**Última modificación del tema:** 2012-06-20_

Si ha instalado la versión de evaluación de Microsoft Lync Server 2013, llegará el momento en que deba actualizar la instalación con una copia con licencia del software. Esto se debe a que la versión de evaluación expira a los 180 días de haberse instalado. No obstante, no tendrá que desinstalar completamente la versión de evaluación para instalar la versión con licencia. En su lugar, una vez que haya adquirido una clave de licencia válida, podrá actualizar la versión de evaluación de Lync Server 2013 llevando a cabo el siguiente procedimiento en cada uno de los equipos que funcionen como Servidor front-end, director o Servidor perimetral de Lync Server. Tenga en cuenta que no tiene que actualizar los equipos que desempeñen otros roles de servidor, como, por ejemplo, un servidor de supervisión o un servidor de archivado.

## Actualizar desde la versión de evaluación de Microsoft Lync Server 2013

Para actualizar un equipo a partir de la versión de evaluación de Lync Server 2013 a una versión con licencia del software:

**Actualizar desde la versión de evaluación de Microsoft Lync Server 2013**

1.  Inicie sesión en el equipo como administrador local.

2.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y el **Shell de administración de Lync Server**.

3.  En el Shell de administración de Lync Server, escriba el siguiente comando y, después, pulse ENTRAR:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Tenga en cuenta que puede que tenga que especificar la ruta completa del archivo server.msi. Encontrará este archivo en la carpeta Instalación de los archivos de instalación de medios por volumen de Lync Server.

4.  Cuando termine de ejecutarse la instalación, escriba lo siguiente desde el símbolo del sistema y, a continuación, pulse ENTRAR:
    
        Enable-CsComputer

5.  Repita este procedimiento en cualquier otro Servidor front-end, director o Servidor perimetral que ejecute una copia de evaluación de Lync Server. Este procedimiento también deberá llevarse a cabo en todos los servidores de sucursal que se hayan implementado usando los archivos de instalación de medios de Lync Server.

Si no está seguro de si un equipo en concreto está ejecutando la versión de evaluación de Lync Server, puede cerciorarse ejecutando el siguiente comando desde el Shell de administración de Lync Server:

    Get-CsServerVersion

El cmdlet [Get-CsServerVersion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsServerVersion) analizará el equipo local y devolverá una de las siguientes opciones:

  - Que la clave de licencia por volumen de Lync Server está instalada en el equipo, lo que significa que no es necesaria ninguna actualización.

  - Que la clave de licencia de evaluación de Lync Server está instalada, lo que significa que el equipo debe actualizarse.

  - Que no es necesaria ninguna clave de licencia por volumen en el equipo. La actualización de la versión de evaluación a la versión con licencia solo es necesaria en los servidores front-end, directores y servidores perimetrales.

