---
title: "Activar servidor tras cierre de puertos del Asistente para config. seguridad en IIS"
TOCTitle: Volver a activar el servidor después de que el Asistente para la configuración de la seguridad cierre los puertos en IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48276676
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Volver a activar el servidor después de que el Asistente para la configuración de la seguridad cierre los puertos en IIS

 

_**Última modificación del tema:** 2012-10-01_

Algunos roles de Lync Server 2013 ejecutan los Servicios web en el puerto 4443 de Servicios de Internet Information Server (IIS). La ejecución del Asistente para la implementación de Lync Server, Bootstrapper.exe, o el uso del cmdlet **Enable-CsComputer** crea una excepción en el firewall y abre el puerto. Si a continuación ejecuta el Asistente para configuración de seguridad de Windows Server 2008 R2 o de Servicios web (u otros scripts de protección), el puerto 4443 se bloqueará y los clientes externos no podrán ponerse en contacto con los fea-web-service. Para volver a abrir el puerto, puede modificar la excepción del firewall directamente o reactivar el servidor.

## Para reactivar el servidor mediante el Asistente para la implementación

1.  En la página del Asistente para la implementación de Lync Server, haga clic en **Ejecutar** junto a **Paso 2: configuración o supresión de componentes de Lync Server** .

2.  En la página **Instalar componentes de Lync Server**, haga clic en **Siguiente**.

3.  Cuando el estado de la tarea aparezca como completado en la página **Ejecución de comandos**, haga clic en **Finalizar**.
    

    > [!NOTE]
    > Para reactivar el servidor, también puede usar bootstrapper.exe o <STRONG>Enable-CsComputer</STRONG>.


