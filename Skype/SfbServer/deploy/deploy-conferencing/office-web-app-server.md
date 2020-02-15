---
title: Configurar la integración con Office Web Apps Server en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la integración entre Office Web Apps Server y Skype empresarial Server para habilitar las presentaciones de PowerPoint para conferencias web.'
ms.openlocfilehash: fee5939e8441457e3cee66e266baacd144ada288
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983925"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurar la integración con Office Web Apps Server en Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración entre Office Web Apps Server y Skype empresarial Server para habilitar las presentaciones de PowerPoint para conferencias web.
  
Skype empresarial Server usa Office Web Apps Server para controlar las presentaciones de PowerPoint para la conferencia Web. Para obtener información sobre las ventajas de este enfoque, consulte [Plan for Conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Para poder configurar Skype empresarial Server para usar Office Web Apps Server, debe asegurarse de que Office Web Apps Server ya está implementado y configurado. Para obtener información sobre Office Web Apps Server, vea el artículo [Deploying The Infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Después de instalar Office Web Apps Server correctamente y de configurar correctamente la granja de servidores Web, debe configurar Skype empresarial Server para comunicarse con el nuevo servidor agregando la dirección URL de detección de Office Web Apps Server a Skype empresarial. Topología de servidores. 
  
> [!NOTE]
> La última iteración de Office Web Apps Server se denomina Office Online Server, que es compatible con Skype empresarial Server. Para obtener más información, consulte la [documentación de Office Online Server](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurar Skype empresarial Server para comunicarse con Office Web Apps Server

Realice lo siguiente para agregar Office Web Apps Server a su topología:
  
1. Abra el generador de topologías de Skype empresarial Server.
    
2. En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
3. En el cuadro de diálogo **Guardar topología como**, escriba el nombre del documento de topología (por ejemplo, **PreWebAppsServerTopology**) en el cuadro **Nombre de archivo** y, después, haga clic en **Guardar**. Esta topología se podrá recuperar y volver a publicar más adelante si detecta algún problema en ella.
    
4. En el generador de topologías, expanda **Skype empresarial Server**, expanda el nombre del sitio, expanda **grupos de servidores front-end Enterprise Edition**, haga clic con el botón secundario en el nombre de uno de los grupos y, a continuación, haga clic en **Editar propiedades**.
    
5. En la pestaña **General** del cuadro de diálogo **Editar propiedades**, busque el encabezado **Asociar Office Web Apps Server** y haga clic en **Nuevo** (o seleccione un Office Web Apps Server de la lista desplegable).
    
6. En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.
    
   - Si Office Web Apps Server está instalado en local y en la misma zona de red que Skype empresarial Server, la opción **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)** no se debe seleccionar.
    
   - Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.
    
7. Haga clic en **Aceptar** en el cuadro de diálogo **Definir nuevo Office Web Apps Server** y, después, haga clic en **Aceptar** en el cuadro de diálogo **Editar propiedades**. La dirección URL de detección se mostrará como una de las asociaciones del grupo de servidores.
    
Este proceso deberá repetirse con cada grupo de servidores que tenga que asociarse a Office Web Apps Server.
  
Una vez que haya agregado la dirección URL de detección a la topología, debe publicar la topología actualizada. Para ello, haga lo siguiente en el Generador de topologías:
  
1. Haga clic en **Acción** y, después, en **Publicar topología**.
    
2. En la página **Publicar la topología** del asistente Publicar topología, haga clic en **Siguiente**.
    
3. En la página **Asistente para publicación completado**, haga clic en **Finalizar**.
    
4. Cierre el Generador de topologías.
    
## <a name="configure-access-for-external-users"></a>Configurar el acceso para los usuarios externos

Si desea que los usuarios externos (es decir, los usuarios que inician sesión desde fuera del firewall de la organización) tengan acceso a las presentaciones de PowerPoint de Office Web Apps Server, tendrá que usar Office Web Apps Server y un servidor proxy inverso. También tendrá que crear y configurar una regla de publicación de sitios web, que le ayudará a asegurarse de que los usuarios puedan conectarse al servidor. 
  
## <a name="validate-the-configuration"></a>Validar la configuración

Después de que se haya agregado Office Web Apps Server a la topología y después de que se haya publicado la topología, verá dos nuevos eventos de registro de eventos en el registro de eventos de Skype empresarial Server. En primer lugar, se debe agregar un evento LS Data MCU (identificador de evento 41034); Este evento informará de que se ha descubierto el servidor de Office Web Apps:
  
 **Se ha descubierto el servidor de conferencia Web de Office Web Apps Server, se ha habilitado el contenido de PowerPoint.**
  
Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:
  
 **Servidor de conferencia web la detección del servidor de Office Web Apps se ha realizado correctamente.**
  
 **Página de moderadores internos de Office Web Apps https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampServer:; embed =**
  
 **Página de asistentes internos de Office Web Apps Server https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp:; embed = true&amp;=**
  
Si ha configurado el acceso para los usuarios externos, también verá algo parecido a lo siguiente:
  
 **Página de moderadores externos de Office Web Apps https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampServer:; embed**
  
 **Página de asistentes internos de Office Web Apps Server <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>:;**
  
Si ve un evento LS Data MCU con el Id. de evento 41033, indicará un error en la detección de Office Web Apps Server. En ese caso, Skype empresarial Server probará tantas veces como sea necesario para descubrir el nuevo servidor de Office Web Apps configurado. Si el proceso de detección falla repetidas veces, deberá quitar Office Web Apps Server del documento de la topología, publicar la topología actualizada y, a continuación, cuando los problemas de conectividad estén resueltos, agregar de nuevo Office Web Apps Server a la topología.
  
Si Office Web Apps Server parece estar configurado correctamente y el proceso de detección lo ha reconocido, puede comprobar que Office Web Apps Server funciona como se esperaba compartiendo una presentación de PowerPoint entre un par de clientes de Skype empresarial. Si el usuario A puede cargar y visualizar la presentación de PowerPoint y el usuario B puede unirse a la reunión y ver esa presentación, significa que Office Web Apps Server funciona.
  
Incluso si Office Web Apps Server parece estar configurado correctamente, es posible que reciba el mensaje de error "algunas características de uso compartido no están disponibles debido a problemas de conectividad de servidor" cuando intenta compartir una presentación de PowerPoint. Si recibe este mensaje de error, reinicie el servidor front-end (o los servidores) asociados con el nuevo servidor de Office Web Apps.
  

