---
title: Configurar los Skype Empresarial Server equipos que se supervisarán
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 'Resumen: instale los archivos del agente de Operations Manager en el equipo de Skype Empresarial Server 2015 que se va a supervisar y configure el equipo para que actúe como proxy System Center usuario.'
ms.openlocfilehash: 8393aab53f8c146a300da0c52a98e470f925e667
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843713"
---
# <a name="configure-the-skype-for-business-server-computers-to-monitor"></a>Configurar los Skype Empresarial Server equipos que se supervisarán

**Resumen:** Instale los archivos de agente de Operations Manager en el equipo Skype Empresarial Server 2015 que se va a supervisar y configure el equipo para que actúe como proxy System Center usuario.

Cada Skype Empresarial Server 2015 que desee supervisar debe poder notificar su existencia al servidor de administración. Para habilitar este proceso, debe instalar los archivos de agente de Operations Manager en cada uno de los equipos que se va a supervisar. Después de instalar los archivos de agente, debe configurar el equipo para que actúe como un System Center proxy. Asegúrese de que primero ha instalado y configurado Skype Empresarial Server en estos equipos antes de llevar a cabo estos procedimientos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalación de un certificado en un nodo de monitor localizado fuera de la red perimetral
<a name="watcher_node_outside"> </a>

System Center Los agentes de Operations Manager que se ejecutan en una red perimetral (como un servidor perimetral de Skype Empresarial Server), fuera de la empresa (como un nodo de monitor de transacciones sintéticas externo) o en un límite de confianza de Active Directory, pueden requerir la configuración de un servidor de puerta de enlace de System Center Operations Manager. Este rol de servidor permite a los agentes que no tienen una relación de confianza con el servidor de administración raíz generar alertas. Para obtener más información, vea [Managing Gateway Servers in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12)).

Si implementa un agente en una de estas ubicaciones, también tendrá que solicitar y configurar un certificado que permita al nodo de monitor enviar alertas a System Center Operations Manager. Para simplificar este proceso, el equipo de Operations Manager creó una serie de utilidades para que pueda solicitar e instalar el tipo correcto de certificado en la PC nodo de supervisión. Para obtener más información y descargar estas utilidades, vea [Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard](https://techcommunity.microsoft.com/t5/system-center-blog/obtaining-certificates-for-non-domain-joined-agents-made-easy/ba-p/340467).

### <a name="installing-the-operation-manager-agent-files"></a>Instalación de los archivos del agente Operations Manager

1. En el System Center de instalación, haga doble clic en **Setup.exe**.

2. En el asistente System Center instalación de Operation Manager, haga clic **en Instalar operations Manager Agent**, en Instalar agente en Instalaciones opcionales

3. En el asistente System Center instalación, en la página De bienvenida al asistente para la instalación de System Center Operations Manager, haga clic en **Siguiente**.

4. En la página Carpeta de destino, seleccione la carpeta donde se instalarán los archivos del agente de Operations Manager y haga clic en **Siguiente**.

5. En la página Configuración del grupo de administración, seleccione **Especificar información del grupo de administración** y haga clic en **Siguiente**.

6. En la página Configuración del grupo de administración, escriba  el nombre del grupo de administración de Operations Manager en el cuadro Nombre de grupo de  administración y, a continuación, escriba el nombre de host del servidor de Operations Manager (por ejemplo, atl-scom-001) en el cuadro Servidor de administración. Si ha cambiado el número de puerto usado por Operations Manager, escriba el nuevo número de puerto en el cuadro Puerto del **servidor de** administración. De lo contrario, deje el puerto en el valor predeterminado de 5723 y, a continuación, haga clic en **Siguiente**.

7. En la página Cuenta de acción del agente, seleccione **Sistema local y** haga clic en **Siguiente**.

8. En la página Microsoft Update, seleccione No quiero usar **Microsoft Update** y haga clic en **Siguiente**.

9. En la página Listo para instalar, haga clic en **Instalar**.

10. En la página Completar el asistente System Center instalación de Operations Manager, haga clic **en Finalizar**.

11. Haga clic en **Salir**.

Para System Center 2012, puede comprobar que el agente se ha creado haciendo clic en Inicio **,** haciendo clic en Todos los **programas,** haciendo clic **en System Center Operations Manager 2012** y, a continuación, haciendo clic en Shell del administrador de **Operaciones 2012**. En el shell de Operations Manager, escriba el siguiente comando Windows PowerShell y, a continuación, presione ENTRAR:
```PowerShell
Get-SCOMAgent
```

Aparecerá una lista de todos los agentes de Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurar el equipo Skype Empresarial Server para participar en la detección System Center datos
<a name="watcher_node_outside"> </a>

Para asegurarse de que el nuevo agente de Skype Empresarial Server participa en el proceso de detección de System Center Operations Manager, debe completar el siguiente procedimiento en cada equipo donde se haya instalado la consola de System Center Operations Manager:

1. En la pestaña Administración, haga clic en **Agente administrado**.

2. Haga clic **en Asistente para** detección y complete el asistente para que se descubra el equipo.

3. Reinicie el servicio del agente de mantenimiento. Reiniciar el servicio forzará la detección de la nueva máquina. Si no reinicia el servicio, el administrador de operaciones podría tardar hasta System Center 4 horas en descubrir el nuevo equipo.

4. Compruebe que no se registraron eventos de error en el registro de eventos de Operations Manager.

5. El equipo donde se inserta correctamente el agente se mostrará en la lista "Administrado por agente" y el equipo donde se instaló el agente manualmente se mostrará en "Administración pendiente", haga clic en el nombre del equipo y apruebe.

6. Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en  **Propiedades**. En el cuadro de diálogo Propiedades, en la pestaña Seguridad, seleccione **Permitir a este agente que actúe como proxy ay detecte objetos administrados en otros equipos** y luego haga clic en **Aceptar**.