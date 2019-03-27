---
title: Configurar los equipos de Skype Empresarial Server equipos que se supervisarán
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 'Resumen: Instalar los archivos del agente Operations Manager en el Skype para Business Server 2015 equipo que se va a supervisar y configurar el equipo para que actúe como un proxy de System Center.'
ms.openlocfilehash: 55d862517eeaad6fbfb567fe4327c375fc1ce2e1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895023"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurar los equipos de Skype Empresarial Server equipos que se supervisarán

**Resumen:** Instalar los archivos del agente Operations Manager en el Skype para Business Server 2015 equipo que se va a supervisar y configurar el equipo para que actúe como un proxy de System Center.

Cada Skype para Business Server 2015 equipo que desea supervisar debe poder Self-notificar su existencia al servidor de administración. Para habilitar este proceso, es necesario instalar los archivos del agente de Operations Manager en cada uno de los equipos que vaya a supervisar. Después de instalar los archivos del agente, debe configurar el equipo para que actúe como proxy de System Center. Asegúrese de que se ha instalado y configurado Skype para Business Server en estos equipos antes de llevar a cabo estos procedimientos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalación de un certificado en un nodo de monitor localizado fuera de la red perimetral
<a name="watcher_node_outside"> </a>

Agentes de System Center Operations Manager que se ejecuta en un perímetro de red (por ejemplo, Skype para servidor perimetral de Business Server), fuera de la empresa (por ejemplo, un nodo de monitor externo transacciones sintéticas) o a través de una confianza de Active Directory puede requerir límite, la configuración de un servidor de puerta de enlace de System Center Operations Manager. Este rol de servidor permite que los agentes que no tienen una relación de confianza con el servidor de administración raíz inicien alertas. Para obtener información detallada, vea [Administración de servidores de puerta de enlace de Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Si implementa a un agente en una de estas ubicaciones, también tendrá que solicitar y configurar un certificado que permite el nodo de monitor enviar alertas a System Center Operations Manager. Para simplificar este proceso, el equipo de Operations Manager ha creado un conjunto de utilidades que permiten solicitar e instalar al tipo de certificado correcto en el equipo de nodo de monitor. Para obtener información detallada y para descargar estas utilidades, consulte [Obtención de certificados para dominios no se unió a los agentes Made Easy con el Asistente para certificados de generación](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Instalación de los archivos del agente Operations Manager

1. En el medio de instalación de System Center, haga doble clic en   **SetupOM.exe**.

2. En el Asistente para la instalación de System Center Operation Manager, haga clic en **Instalar el agente Operations Manager**, de instalar el agente en instalaciones opcional

3. En el Asistente para el programa de instalación de System Center, en la bienvenida a la página del Asistente para la instalación de System Center Operations Manager, haga clic en **siguiente**.

4. En la página carpeta de destino, seleccione la carpeta donde se va a instalar los archivos del agente Operations Manager y, haga clic en **siguiente**.

5. En la página Configuración del grupo de administración, seleccione **Especificar información del grupo de administración** y después haga clic en **Siguiente**.

6. En la página Configuración del grupo de administración, escriba el nombre de su grupo de administración de Operations Manager en el cuadro **Nombre de grupo de administración** y, a continuación, escriba el nombre de host de su servidor de Operations Manager (por ejemplo, atl-scom-001) en el servidor de administración de ** **cuadro. Si ha cambiado el número de puerto que Operations Manager usa, escriba el nuevo número en el cuadro **Puerto del servidor de administración**. De lo contrario, deje el puerto en el valor predeterminado 5723 y haga clic en **Siguiente**.

7. En la página Cuenta de acción del agente, seleccione **Sistema local** y haga clic en **Siguiente**.

8. En la página Microsoft Update, seleccione **No quiero usar Microsoft Update** y haga clic en **Siguiente**.

9. En la página Preparado para instalar, haga clic en **Instalar**.

10. En la página Finalizando la página Asistente para la instalación de System Center Operations Manager, haga clic en **Finalizar**.

11. Haga clic en **Salir**.

Para System Center 2012, puede comprobar que el agente se ha creado hace clic en **Inicio**, haciendo clic en **Todos los programas**, haciendo clic en **System Center Operations Manager 2012**y, a continuación, haciendo clic en **Shell de 2012 de Operations Manager**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```
Get-SCOMAgent
```

Aparecerá en pantalla una lista de todos los agentes de Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configuración del equipo de  Skype Empresarial Server para participar en la detección en System Center
<a name="watcher_node_outside"> </a>

Para asegurarse de que su nuevo Skype para el agente de Business Server participa en el proceso de detección para System Center Operations Manager, debe completar el procedimiento siguiente en cada equipo donde se ha instalado la consola de System Center Operations Manager:

1. En la pestaña Administración, haga clic en **Agente administrado**.

2. Haga clic en **Asistente para la detección** y complete el asistente para que el equipo que se debe descubrir.

3. Reinicie el servicio Agente de estado. Al reiniciar este servicio se forzará el descubrimiento del nuevo equipo. Si no se reinicie el servicio, podría demorar hasta 4 horas antes de la máquina nueva se detecta mediante System Center Operations Manager.

4. Compruebe que no se registraron eventos de error en el registro de eventos de Operations Manager.

5. El equipo donde el agente se inserta correctamente se mostrará en la lista "Agente administrado" y el equipo donde se ha instalado manualmente el agente volverá a mostrarse en "Administración de pendiente", haga clic en el nombre del equipo y aprobar.

6. Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en **Propiedades**. En el cuadro de diálogo Propiedades, en la pestaña Seguridad, seleccione **Permitir a este agente que actúe como proxy ay detecte objetos administrados en otros equipos** y, a continuación, haga clic en **Aceptar**.


