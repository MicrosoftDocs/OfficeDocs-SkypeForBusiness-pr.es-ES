---
title: Configurar los equipos de Skype empresarial Server que se supervisarán
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Instale los archivos del agente Operations Manager en el equipo con Skype empresarial Server 2019 para que se supervise y configure el equipo para que actúe como un proxy de System Center.'
ms.openlocfilehash: 062dfeb4b03cbe68de21bcb4ea8722bf0f666070
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150491"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurar los equipos de Skype empresarial Server que se supervisarán

**Resumen:** Instale los archivos del agente Operations Manager en el equipo de Skype empresarial Server 2019 que se va a supervisar y configure el equipo para que actúe como un proxy de System Center.

Cada equipo de Skype empresarial Server 2019 que desee supervisar debe ser capaz de informar a sí mismo sobre su existencia en el servidor de administración. Para habilitar este proceso, debe instalar los archivos del agente Operations Manager en cada uno de los equipos que se va a supervisar. Después de instalar los archivos del agente, debe configurar el equipo para que actúe como un proxy de System Center. Asegúrese de haber instalado y configurado primero Skype empresarial Server en estos equipos antes de llevar a cabo estos procedimientos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalación de un certificado en un nodo de monitor localizado fuera de la red perimetral
<a name="watcher_node_outside"> </a>

Los agentes de System Center Operations Manager que se ejecutan en una red perimetral (como un servidor perimetral de Skype empresarial Server), fuera de la empresa (como un nodo externo de monitor de transacciones sintéticas) o en un límite de confianza de Active Directory, pueden requerir la configuración de un servidor de puerta de enlace de System Center Operations Manager. Este rol de servidor permite que los agentes que no tienen una relación de confianza con el servidor de administración raíz generen alertas. Para obtener más información, consulte [administrar servidores de puerta de enlace en Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).

Si implementa un agente en una de estas ubicaciones, también tendrá que solicitar y configurar un certificado que permita al nodo de monitor enviar alertas a System Center Operations Manager. Para simplificar este proceso, el equipo de Operations Manager creó una serie de utilidades para que pueda solicitar e instalar el tipo correcto de certificado en la PC nodo de supervisión. Para obtener más información y para descargar estas utilidades, consulte [obtención de certificados para agentes no Unidos a un dominio fácilmente con el Asistente para generación de certificados](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Instalación de los archivos del agente Operations Manager

1. En los medios de configuración de System Center, haga doble clic en **setup. exe**.

2. En el Asistente para la instalación de System Center Operations Manager, haga clic en **instalar agente de Operations Manager**, en instalar agente en instalaciones opcionales.

3. En el Asistente para la instalación de System Center, en la página éste es el Asistente para la instalación de System Center Operations Manager, haga clic en **siguiente**.

4. En la página carpeta de destino, seleccione la carpeta en la que se instalarán los archivos del agente de Operations Manager y haga clic en **siguiente**.

5. En la página Configuración del grupo de administración, seleccione **especificar información del grupo de administración** y haga clic en **siguiente**.

6. En la página Configuración del grupo de administración, escriba el nombre del grupo de administración de Operations Manager en el cuadro **nombre del grupo de administración** y, a continuación, escriba el nombre de host del servidor de Operations Manager (por ejemplo, ATL-SCOM-001) en el cuadro servidor de **Administración** . Si cambió el número de puerto que usa Operations Manager, escriba el nuevo número de puerto en el cuadro **Puerto del servidor de administración** . En caso contrario, deje el puerto en el valor predeterminado de 5723 y, a continuación, haga clic en **siguiente**.

7. En la página cuenta de acción del agente, seleccione **sistema local** y haga clic en **siguiente**.

8. En la página Microsoft Update, seleccione **no quiero usar Microsoft Update** y haga clic en **siguiente**.

9. En la página Listo para instalar, haga clic en **Instalar**.

10. En la página finalización del Asistente para la instalación de System Center Operations Manager, haga clic en **Finalizar**.

11. Haga clic en **Salir**.

Para System Center 2012, puede comprobar que el agente se ha creado haciendo clic en **Inicio**, en **todos los programas**, en **System Center Operations Manager 2012**y, a continuación, en **Operations 2012 Manager Shell**. En el shell de Operations Manager, escriba el siguiente comando de Windows PowerShell y, a continuación, presione ENTRAR:
```PowerShell
Get-SCOMAgent
```

Aparecerá una lista de todos los agentes de Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configuración del equipo de Skype empresarial Server para participar en la detección de System Center
<a name="watcher_node_outside"> </a>

Para asegurarse de que el nuevo agente de Skype empresarial Server participa en el proceso de detección de System Center Operations Manager, debe completar el siguiente procedimiento en cada equipo en el que se haya instalado la consola de System Center Operations Manager:

1. En la pestaña Administración, haga clic en **Agente administrado**.

2. Haga clic en **Asistente para detección** y complete el Asistente para el equipo que se va a detectar.

3. Reinicie el servicio de agente de estado. El reinicio del servicio impondrá la detección del nuevo equipo. Si no reinicia el servicio, puede tardar hasta 4 horas antes de que System Center Operations Manager detecte el nuevo equipo.

4. Compruebe que no se haya registrado ningún evento de error en el registro de eventos de Operations Manager.

5. El equipo en el que se inserta correctamente el agente se mostrará en la lista "administrado por el agente" y el equipo en el que se instaló manualmente el agente se mostrará en "administración pendiente", haga clic en el nombre del equipo y en aprobar.

6. Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en  **Propiedades**. En el cuadro de diálogo Propiedades, en la pestaña Seguridad, seleccione **Permitir a este agente que actúe como proxy ay detecte objetos administrados en otros equipos** y luego haga clic en **Aceptar**.


