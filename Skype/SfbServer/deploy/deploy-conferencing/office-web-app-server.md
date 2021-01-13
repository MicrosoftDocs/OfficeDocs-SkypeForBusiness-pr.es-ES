---
title: Configurar la integración con Office Web Apps Server en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Resumen: lea este tema para obtener información sobre cómo configurar la integración entre Office Web Apps Server y Skype Empresarial Server para habilitar presentaciones de PowerPoint para conferencias web.'
ms.openlocfilehash: 005bd9fe7d7fece7d488935002e7146fc5a9ffe4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820470"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurar la integración con Office Web Apps Server en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración entre Office Web Apps Server y Skype Empresarial Server para habilitar presentaciones de PowerPoint para conferencias web.
  
Skype Empresarial Server emplea Office Web Apps Server para administrar presentaciones de PowerPoint para conferencias web. Para obtener información sobre las ventajas de este enfoque, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Antes de configurar Skype Empresarial Server para usar Office Web Apps Server, debe asegurarse de que Office Web Apps Server ya está implementado y configurado. Para obtener información sobre Office Web Apps Server, vea el artículo [Implementar la infraestructura: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Una vez que Office Web Apps Server se haya instalado correctamente y configurado correctamente la granja de servidores web, deberá configurar Skype Empresarial Server para comunicarse con el nuevo servidor agregando la dirección URL de detección de Office Web Apps Server a la topología de Skype Empresarial Server. 
  
> [!NOTE]
> La iteración más reciente de Office Web Apps Server se denomina Office Online Server, que es compatible con Skype Empresarial Server. Para obtener más información, consulte la [documentación de Office Online Server.](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx) 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurar Skype Empresarial Server para comunicarse con Office Web Apps Server

Realice lo siguiente para agregar Office Web Apps Server a su topología:
  
1. Abra el Generador de topologías de Skype Empresarial Server.
    
2. En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
3. En el cuadro de diálogo **Guardar topología como**, escriba el nombre del documento de topología (por ejemplo, **PreWebAppsServerTopology**) en el cuadro **Nombre de archivo** y, después, haga clic en **Guardar**. Esta topología se podrá recuperar y volver a publicar más adelante si detecta algún problema en ella.
    
4. En el Generador de topologías, expanda Skype Empresarial **Server,** expanda el nombre de su sitio, expanda Grupos de servidores **front-end Enterprise Edition,** haga clic con el botón secundario en el nombre de uno de los grupos de servidores y, a continuación, haga clic en Editar **propiedades.**
    
5. En la pestaña **General** del cuadro de diálogo **Editar propiedades**, busque el encabezado **Asociar Office Web Apps Server** y haga clic en **Nuevo** (o seleccione un Office Web Apps Server de la lista desplegable).
    
6. En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.
    
   - Si Office Web Apps Server está instalado localmente y en la misma zona de red que Skype Empresarial Server, no se debe seleccionar la opción Office Web Apps Server se implementa en una red externa **(es decir, perimetral/Internet).**
    
   - Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.
    
7. Haga clic en **Aceptar** en el cuadro de diálogo **Definir nuevo Office Web Apps Server** y, después, haga clic en **Aceptar** en el cuadro de diálogo **Editar propiedades**. A continuación, la dirección URL de detección aparecerá como una de las asociaciones del grupo.
    
Este proceso deberá repetirse con cada grupo de servidores que tenga que asociarse a Office Web Apps Server.
  
Después de agregar la dirección URL de detección a la topología, debe publicar la topología actualizada. Para ello, haga lo siguiente en el Generador de topologías:
  
1. Haga clic en **Acción** y, después, en **Publicar topología**.
    
2. En la página **Publicar la topología** del asistente Publicar topología, haga clic en **Siguiente**.
    
3. En la página **Asistente para publicación completado**, haga clic en **Finalizar**.
    
4. Cierre el Generador de topologías.
    
## <a name="configure-access-for-external-users"></a>Configurar el acceso para usuarios externos

Si desea que los usuarios externos (es decir, los usuarios que inician sesión desde fuera del firewall de la organización) tengan acceso a las presentaciones de PowerPoint de Office Web Apps Server, deberá usar Office Web Apps Server y un servidor proxy inverso. También deberá crear y configurar una regla de publicación de sitios web, lo que ayudará a garantizar que los usuarios puedan conectarse al servidor. 
  
## <a name="validate-the-configuration"></a>Validar la configuración

Después de agregar Office Web Apps Server a la topología y después de publicarla, debería ver dos nuevos eventos de registro de eventos en el registro de eventos de Skype Empresarial Server. En primer lugar, se debe agregar un evento MCU de datos LS (identificador de evento 41034); este evento informa de que se ha detectado Office Web Apps Server:
  
 **Se detecta el servidor de conferencia web de Office Web Apps Server, el contenido de PowerPoint está habilitado.**
  
Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:
  
 **La detección de Office Web Apps Server del servidor de conferencia web ha sido correcta.**
  
 **Página de moderador interno de Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**
  
 **Página de asistentes internos de Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**
  
Si ha configurado el acceso para usuarios externos, también verá algo similar a:
  
 **Página de moderador externo de Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed**
  
 **Página de asistentes internos de Office Web Apps Server: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
Si ve un evento LS Data MCU con el Id. de evento 41033, indicará un error en la detección de Office Web Apps Server. En ese caso, Skype Empresarial Server lo intentará tantas veces como sea necesario para descubrir el servidor de Office Web Apps recién configurado. Si el proceso de detección falla repetidas veces, deberá quitar Office Web Apps Server del documento de la topología, publicar la topología actualizada y, a continuación, cuando los problemas de conectividad estén resueltos, agregar de nuevo Office Web Apps Server a la topología.
  
Si Office Web Apps Server parece estar configurado correctamente y ha sido reconocido por el proceso de detección, puede comprobar que Office Web Apps Server funciona según lo esperado compartiendo una presentación de PowerPoint entre un par de clientes de Skype Empresarial. Si el usuario A puede cargar y visualizar la presentación de PowerPoint y el usuario B puede unirse a la reunión y ver esa presentación, significa que Office Web Apps Server funciona.
  
Incluso si Office Web Apps Server parece estar configurado correctamente, es posible que reciba el mensaje de error "Algunas características de uso compartido no están disponibles debido a problemas de conectividad del servidor" al intentar compartir una presentación de PowerPoint. Si recibe ese mensaje de error, debe reiniciar el servidor front-end (o servidores) asociado con el nuevo office Web Apps Server.
  

