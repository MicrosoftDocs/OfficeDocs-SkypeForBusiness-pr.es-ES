---
title: Supervisar archivos de registro de seguimiento de solicitudes de IIS
TOCTitle: Supervisar archivos de registro de seguimiento de solicitudes de IIS
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48276428
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supervisar archivos de registro de seguimiento de solicitudes de IIS

 

_**Última modificación del tema:** 2016-12-08_

Al habilitar el seguimiento de solicitudes de Servicios de Internet Information Server (IIS) para el servicio de movilidad de Lync Server, los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día. El registro de seguimiento de IIS está habilitado de manera predeterminada. Debe supervisar los Servidores front-end para asegurarse de que no se quedan sin espacio en disco.

De manera predeterminada, IIS almacena los archivos de registro en %SystemDrive%\\inetpub\\logs\\LogFiles.

Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Para más información sobre el comando **httpLogging**, vea [http://go.microsoft.com/fwlink/?linkid=234927\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=234927%26clcid=0xc0a).

