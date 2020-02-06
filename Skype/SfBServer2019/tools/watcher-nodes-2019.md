---
title: Configurar los equipos de Skype Empresarial Server equipos que se supervisarán
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Instale los archivos del agente de Operations Manager en el servidor de Skype empresarial Server 2019 que se va a supervisar y configure el equipo para que funcione como un proxy de System Center.'
ms.openlocfilehash: 162b2dc0b50b7da5246d69d64b0bdb307212c139
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799650"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurar los equipos de Skype Empresarial Server equipos que se supervisarán

**Resumen:** Instale los archivos del agente Operations Manager en el servidor de Skype para empresas 2019 que se va a supervisar y configure el equipo para que funcione como un proxy de System Center.

Cada equipo con Skype empresarial Server 2019 que desee supervisar debe poder denunciar su existencia en el servidor de administración. Para habilitar este proceso, es necesario instalar los archivos del agente de Operations Manager en cada uno de los equipos que vaya a supervisar. Después de instalar los archivos del agente, debe configurar el equipo para que actúe como proxy de System Center. Asegúrese de haber instalado y configurado primero Skype empresarial Server en estos equipos antes de llevar a cabo estos procedimientos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalación de un certificado en un nodo de monitor localizado fuera de la red perimetral
<a name="watcher_node_outside"> </a>

Los agentes de System Center Operations Manager que se ejecutan en una red perimetral (como un servidor perimetral de Skype empresarial Server), fuera de la empresa (como un nodo de monitor de transacciones sintéticas externo) o a través de un límite de confianza de Active Directory, pueden requerir la configuración de un servidor de puerta de enlace System Center Operations Manager. Este rol de servidor permite que los agentes que no tienen una relación de confianza con el servidor de administración raíz inicien alertas. Para obtener más información, vea [administrar servidores de puerta de enlace en Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Si implementa un agente en una de estas ubicaciones, también tendrá que solicitar y configurar un certificado que permita al nodo de monitor enviar alertas a System Center Operations Manager. Para simplificar este proceso, el equipo de Operations Manager ha creado un conjunto de utilidades que le permiten solicitar e instalar el tipo de certificado correcto en el equipo del nodo de observador. Para obtener más información y para descargar estas utilidades, vea [obtener certificados para agentes no Unidos a un dominio simplificado con el Asistente para generación de certificados](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Instalación de los archivos del agente Operations Manager

1. En el medio de instalación de System Center, haga doble clic en   **SetupOM.exe**.

2. En el Asistente para la configuración de System Center Operation Manager, haga clic en **instalar agente Operations Manager**, en instalar agente, en instalaciones opcionales

3. En el Asistente de configuración de System Center, en la página Asistente para la instalación de System Center Operations Manager, haga clic en **siguiente**.

4. En la página carpeta de destino, seleccione la carpeta en la que se instalarán los archivos del agente de Operations Manager y haga clic en **siguiente**.

5. En la página Configuración del grupo de administración, seleccione **Especificar información del grupo de administración** y después haga clic en **Siguiente**.

6. En la página Configuración del grupo de administración, escriba el nombre del grupo de administración de Operations Manager en el cuadro **nombre del grupo de administración** y, a continuación, escriba el nombre de host del servidor de Operations Manager (por ejemplo, ATL-SCOM-001) en el cuadro servidor de **Administración** . Si ha cambiado el número de puerto que Operations Manager usa, escriba el nuevo número en el cuadro **Puerto del servidor de administración**. De lo contrario, deje el puerto en el valor predeterminado 5723 y haga clic en **Siguiente**.

7. En la página Cuenta de acción del agente, seleccione **Sistema local** y haga clic en **Siguiente**.

8. En la página Microsoft Update, seleccione **No quiero usar Microsoft Update** y haga clic en **Siguiente**.

9. En la página Preparado para instalar, haga clic en **Instalar**.

10. En la página finalización del Asistente para la instalación de System Center Operations Manager, haga clic en **Finalizar**.

11. Haga clic en **Salir**.

Para System Center 2012, puede comprobar que el agente se ha creado haciendo clic en **Inicio**, en **todos los programas**, en **System Center Operations Manager 2012**y, a continuación, en **Operations 2012 Manager Shell**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```PowerShell
Get-SCOMAgent
```

Aparecerá en pantalla una lista de todos los agentes de Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configuración del equipo de  Skype Empresarial Server para participar en la detección en System Center
<a name="watcher_node_outside"> </a>

Para asegurarse de que el nuevo agente de Skype empresarial participe en el proceso de descubrimiento de System Center Operations Manager, debe completar el siguiente procedimiento en cada equipo en el que se haya instalado la consola de System Center Operations Manager:

1. En la pestaña Administración, haga clic en **Agente administrado**.

2. Haga clic en **Asistente para la detección** y complete el asistente para que el equipo que se debe descubrir.

3. Reinicie el servicio Agente de estado. Al reiniciar este servicio se forzará el descubrimiento del nuevo equipo. Si no reinicia el servicio, puede demorar hasta 4 horas antes de que System Center Operations Manager Descubra el nuevo equipo.

4. Compruebe que no se registraron eventos de error en el registro de eventos de Operations Manager.

5. El equipo en el que se inserta el agente correctamente se mostrará en la lista "administrado por el agente" y el equipo en el que se instaló manualmente el agente se mostrará en "administración pendiente", haga clic en el nombre del equipo y en aprobar.

6. Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en **Propiedades**. En el cuadro de diálogo Propiedades, en la pestaña Seguridad, seleccione **Permitir a este agente que actúe como proxy ay detecte objetos administrados en otros equipos** y, a continuación, haga clic en **Aceptar**.


