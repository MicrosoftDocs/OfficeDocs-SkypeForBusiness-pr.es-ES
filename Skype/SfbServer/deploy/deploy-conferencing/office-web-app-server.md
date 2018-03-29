---
title: Configurar la integración con Office Web Apps Server en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Resumen: Leer este tema para obtener información sobre cómo configurar la integración entre el servidor de Office Web Apps y Skype para Business Server 2015 para habilitar las presentaciones de PowerPoint para conferencias web.'
ms.openlocfilehash: da6b5765cf62fc97fcc20b72e2411db306b37f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server-2015"></a>Configurar la integración con Office Web Apps Server en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a configurar la integración entre el servidor de Office Web Apps y Skype para Business Server 2015 para habilitar las presentaciones de PowerPoint para conferencias web.
  
Skype para Business Server emplea el servidor de Office Web Apps para controlar las presentaciones de PowerPoint para conferencias web. Para obtener información acerca de las ventajas de este enfoque, consulte [Plan de conferencia en Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md).
  
Para poder configurar Skype para Business Server usar Office Web Apps Server, debe asegurarse de que Office Web Apps Server ya está implementado y configurado. Para obtener información acerca de servidor de Office Web Apps, vea el artículo [implementar la infraestructura: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Una vez que se ha instalado correctamente el servidor de Office Web Apps y su granja Web configurado correctamente, a continuación, debe configurar Skype para Business Server para comunicarse con el nuevo servidor agregando la dirección URL de detección de servidor de Office Web Apps para su Skype para empresas Topología de servidor. 
  
> [!NOTE]
> La iteración más reciente de Office Web Apps Server se denomina servidor en línea de Office, que es compatible con Skype para Business Server 2015. Para obtener más detalles, consulte la [documentación del servidor de Office Online](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurar Skype para Business Server para comunicarse con el servidor de Office Web Apps

Realice lo siguiente para agregar Office Web Apps Server a su topología:
  
1.  Abre Skype para el generador de topología de servidor empresarial.
    
2. En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.
    
3. En el cuadro de diálogo **Guardar topología como**, escriba el nombre del documento de topología (por ejemplo, **PreWebAppsServerTopology**) en el cuadro **Nombre de archivo** y, después, haga clic en **Guardar**. Esta topología se podrá recuperar y volver a publicar más adelante si detecta algún problema en ella.
    
4. En el Generador de topologías, expanda **Skype Empresarial Server**, el nombre de su sitio y **Grupos de servidores front-end Enterprise Edition**, haga clic con el botón derecho en uno de los grupos de servidores y, luego, haga clic en **Editar propiedades**.
    
5. En la pestaña **General** del cuadro de diálogo **Editar propiedades**, busque el encabezado **Asociar Office Web Apps Server** y haga clic en **Nuevo** (o seleccione un Office Web Apps Server de la lista desplegable).
    
6. En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.
    
  - Si el servidor de Office Web Apps está instalado local y en la misma zona de red como Skype para, a continuación, la opción de Business Server **que Office Web Apps Server se implementa en una red externa (es decir, perimetral e Internet)** no se elegirán.
    
  - Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.
    
7. Haga clic en **Aceptar** en el cuadro de diálogo **Definir nuevo servidor de Office Web Apps** y, después, haga clic en **Aceptar** en el cuadro de diálogo **Editar propiedades**. La dirección URL de detección de Office Online aparecerá como una de las asociaciones del grupo de servidores.
    
Este proceso deberá repetirse con cada grupo de servidores que tenga que asociarse a Office Web Apps Server.
  
Una vez que haya agregado la dirección URL de descubrimiento a la topología, deberá publicar la topología actualizada. Para ello, haga lo siguiente en el Generador de topologías:
  
1. Haga clic en **Acción** y, después, en **Publicar topología**.
    
2. En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.
    
3. En la página **Asistente para publicación completado**, haga clic en **Finalizar**.
    
4. Cierre el Generador de topologías.
    
## <a name="configure-access-for-external-users"></a>Configurar el acceso para usuarios externos

Si desea que los usuarios externos (es decir, los usuarios iniciar sesión desde fuera de firewall de la organización) para tener acceso a las presentaciones de PowerPoint de servidor de Office Web Apps, entonces necesitará utilizar un servidor proxy inverso y servidor de Office Web Apps. También tendrá que crear y configurar una regla de publicación de sitio web, que le ayudará a asegurarse de que los usuarios puedan conectarse al servidor. 
  
## <a name="validate-the-configuration"></a>Validar la configuración

Después de agregar a la topología de servidor de Office Web Apps, y después se ha publicado dicha topología, verá dos nuevos eventos de registro de sucesos en el Skype para el registro de sucesos del servidor de empresa. En primer lugar, debe agregarse un evento LS datos MCU (Id. de evento 41034); Este evento informará de que el servidor de Office Web Apps ha descubierto:
  
 **Se ha detectado el servidor de conferencia web Office Web Apps Server, se ha habilitado el contenido de PowerPoint.**
  
Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:
  
 **Se ha detectado correctamente el servidor de conferencia web de Office Web Apps Server.**
  
 **Página de Office Web Apps Server interno moderador: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0 &amp;incrustar =**
  
 **Página Asistente interno de Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0 &amp;incrustar = true&amp;=**
  
Si ha configurado el acceso a usuarios externos, verá también algo similar a lo siguiente:
  
 **Página de Office Web Apps Server externos moderador: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0 &amp;incrustar**
  
 **Página Asistente interno de Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0 &amp;incrustar = true&amp;**
  
Si ve un evento de LS datos MCU con el identificador de evento de 41033 que significa que la detección de servidor de Office Web Apps ha fallado. En ese caso, Skype para Business Server intentará tantas veces como sea necesario para descubrir el servidor recién configurado Office Web Apps. Si el proceso de descubrimiento falla varias veces debe quitar Office Web Apps Server de su documento de topología, publicar la topología actualizados y, a continuación, intente agregar Office Web Apps Server a la topología una vez solucionados los problemas de conectividad.
  
Si Office Web Apps Server parece estar configurado correctamente y ha sido reconocido por el proceso de descubrimiento puede comprobar que Office Web Apps Server funciona como se esperaba al compartir una presentación de PowerPoint entre un par de Skype para clientes empresariales. Si el usuario A puede cargar y mostrar la presentación de PowerPoint, y si el usuario B puede unirse a la reunión y ver esa presentación está trabajando el servidor de Office Web Apps.
  
Aunque parece que Office Web Apps Server esté configurado correctamente, podría potencialmente recibir el mensaje de error "algunas funciones compartidas no están disponibles debido a problemas de conectividad de servidor" cuando intenta compartir una presentación de PowerPoint. Si recibe ese mensaje de error, debe reiniciar el servidor de Front-End (o servidores) asociados con el nuevo servidor de aplicaciones Web de Office.
  

