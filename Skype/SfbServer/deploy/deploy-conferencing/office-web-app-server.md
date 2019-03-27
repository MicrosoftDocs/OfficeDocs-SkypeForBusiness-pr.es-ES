---
title: Configurar la integración con Office Web Apps Server en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la integración entre Office Web Apps Server y Skype para Business Server para habilitar las presentaciones de PowerPoint para las conferencias web.'
ms.openlocfilehash: 69cdbd50387f2e3267a0fc2acb38e47260970578
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892578"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurar la integración con Office Web Apps Server en Skype para Business Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración entre Office Web Apps Server y Skype para Business Server para habilitar las presentaciones de PowerPoint para las conferencias web.
  
Skype para Business Server emplea Office Web Apps Server para administrar las presentaciones de PowerPoint para las conferencias web. Para obtener información acerca de las ventajas de este enfoque, consulte [Plan para las conferencias en Skype para Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Antes de poder configurar Skype para Business Server usar Office Web Apps Server, debe asegurarse de que Office Web Apps Server ya se ha implementado y configurado. Para obtener información acerca de Office Web Apps Server, vea el artículo [implementar la infraestructura: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Una vez que se ha instalado correctamente Office Web Apps Server y la granja de servidores Web configurado correctamente, a continuación, debe configurar Skype para Business Server para comunicarse con el nuevo servidor mediante la adición de la dirección URL de detección de Office Web Apps Server para su Skype para la empresa Topología de servidores. 
  
> [!NOTE]
> La iteración más reciente de Office Web Apps Server se denomina servidor en línea de Office, que es compatible con Skype para Business Server. Para obtener más detalles, consulte la [documentación de Office Server en línea](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configuración de Skype para Business Server para comunicarse con Office Web Apps Server

Realice lo siguiente para agregar Office Web Apps Server a su topología:
  
1. Abra Skype para Business Server Topology Builder.
    
2. En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.
    
3. En el cuadro de diálogo **Guardar topología como**, escriba el nombre del documento de topología (por ejemplo, **PreWebAppsServerTopology**) en el cuadro **Nombre de archivo** y, después, haga clic en **Guardar**. Esta topología se podrá recuperar y volver a publicar más adelante si detecta algún problema en ella.
    
4. En el Generador de topologías, expanda **Skype Empresarial Server**, el nombre de su sitio y **Grupos de servidores front-end Enterprise Edition**, haga clic con el botón derecho en uno de los grupos de servidores y, luego, haga clic en **Editar propiedades**.
    
5. En la pestaña **General** del cuadro de diálogo **Editar propiedades**, busque el encabezado **Asociar Office Web Apps Server** y haga clic en **Nuevo** (o seleccione un Office Web Apps Server de la lista desplegable).
    
6. En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.
    
   - Si Office Web Apps Server está instalada localmente y en la misma zona de red como Skype para Business Server, a continuación, la opción de **que Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)** no se debe seleccionar.
    
   - Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.
    
7. Haga clic en **Aceptar** en el cuadro de diálogo **Definir nuevo servidor de Office Web Apps** y, después, haga clic en **Aceptar** en el cuadro de diálogo **Editar propiedades**. La dirección URL de detección de Office Online aparecerá como una de las asociaciones del grupo de servidores.
    
Este proceso deberá repetirse con cada grupo de servidores que tenga que asociarse a Office Web Apps Server.
  
Una vez que haya agregado la dirección URL de descubrimiento a la topología, deberá publicar la topología actualizada. Para ello, haga lo siguiente en el Generador de topologías:
  
1. Haga clic en **Acción** y, después, en **Publicar topología**.
    
2. En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.
    
3. En la página **Asistente para publicación completado**, haga clic en **Finalizar**.
    
4. Cierre el Generador de topologías.
    
## <a name="configure-access-for-external-users"></a>Configurar el acceso para usuarios externos

Si desea que los usuarios externos (es decir, los usuarios que inician sesión desde fuera del firewall de la organización) para tener acceso a las presentaciones de PowerPoint de Office Web Apps Server, a continuación, tendrá que usar Office Web Apps Server y un servidor proxy inverso. También tendrá que crear y configurar una regla de publicación de sitio web, que le ayudará a asegurarse de que los usuarios puedan conectarse al servidor. 
  
## <a name="validate-the-configuration"></a>Validar la configuración

Después de Office Web Apps Server se ha agregado a la topología y, cuando se haya publicado dicha topología, debería ver dos nuevos eventos de registro de eventos en el Skype para el registro de eventos de servidor empresarial. En primer lugar, se debe agregar un evento LS datos MCU (identificador de evento 41034); Este evento informará que se ha detectado el servidor de aplicaciones Web de Office:
  
 **Se ha detectado el servidor de conferencia web Office Web Apps Server, se ha habilitado el contenido de PowerPoint.**
  
Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:
  
 **Se ha detectado correctamente el servidor de conferencia web de Office Web Apps Server.**
  
 **Página de presentador interno de Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; incrustar =**
  
 **Página de asistente interno de Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; incrustar = true&amp;=**
  
Si ha configurado el acceso de usuarios externos, también verá algo parecido a:
  
 **Página de presentador externo de Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; incrustar**
  
 **Página de asistente interno de Office Web Apps Server: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
Si ve un evento LS datos MCU con el identificador de evento de 41033 lo que significa que la detección de Office Web Apps Server que ha generado un error. En ese caso, Skype para Business Server intentará tantas veces como sea necesario para detectar recién configurado Office Web Apps Server. Si el proceso de detección se produce un error repetidamente debe quitar Office Web Apps Server de su documento de topología, publicar la topología actualizada y, a continuación, intente agregar Office Web Apps Server vuelve a la topología después de que se han solucionado los problemas de conectividad.
  
Si Office Web Apps Server parece que esté configurado correctamente y ha sido reconocido por el proceso de detección puede comprobar que Office Web Apps Server funciona según lo esperado al compartir una presentación de PowerPoint entre un par de Skype para clientes empresariales. Si el usuario A puede cargar y mostrar la presentación de PowerPoint y usuario B, a continuación, puede unirse a la reunión y vea esa presentación funciona Office Web Apps Server.
  
Incluso si Office Web Apps Server parece estar correctamente configuradas, podría potencialmente recibirá el mensaje de error "algunas características de uso compartido no están disponibles debido a problemas de conectividad de servidor" cuando intenta compartir una presentación de PowerPoint. Si recibe dicho mensaje de error debe reiniciar el servidor de Front-End (o servidores) asociado con el nuevo Office Web Apps Server.
  

