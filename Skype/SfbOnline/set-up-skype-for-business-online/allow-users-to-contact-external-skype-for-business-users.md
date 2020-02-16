---
title: Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: 394613e3137c65e814cc08dd898ec797d560d1c6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010943"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial

> [!NOTE]
> La Federación de Skype empresarial no está disponible para Office 365 operado por 21Vianet y las organizaciones de Office 365 Germany. 
  
Siga los pasos de este artículo cuando:
  
- Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.
    
- Desee que las personas de su empresa puedan usar Skype Empresarial para ponerse en contacto con personas de empresas específicas de fuera de su organización.
    
- Desea que cualquier persona del mundo que use Skype empresarial pueda encontrarse y ponerse en contacto con usted, usando su dirección de correo electrónico. Esto funcionará automáticamente si usted y el otro usuario usan la configuración predeterminada de Skype Empresarial. De lo contrario, deben asegurarse de que la configuración no esté bloqueando su dominio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicaciones entre empresas para los usuarios
<a name="bk_preview"> </a>

Para ello, debe tener [permisos de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en Office 365 en ambas organizaciones.

![Un icono que muestra el logotipo](../images/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Teams**
  
1. Inicie sesión con su cuenta de administrador de Office 365. 
    
2. En el centro de administración, vaya a**equipos**del centro de **Administración** > .
    
    ![Elija el administrador de Teams.](../images/MS-Teams-Admin.png)
  
3. En el **centro de equipos**, elija **portal** 
 ![heredado de **Skype** > elija el portal heredado de SfB.](../images/SFBlegacy-size65.png)
 
4. En el **centro de administración de Skype empresarial** , elija**comunicaciones externas**de la **organización** > .
5. Para configurar la comunicación con una empresa específica o con usuarios de otro dominio, en el cuadro desplegable, elija **activado solo para los dominios permitidos**.
    
    O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.
    
6. En **dominios bloqueados o permitidos**, elija **+** y agregue el nombre del dominio que desea permitir.
    
7. Asegúrese de que el administrador de la otra organización Realice estos mismos pasos en el **centro de administración de Skype empresarial**. Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.
    
8. Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.
    
    Si su organización usa una solución de firewall diferente para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a los siguientes [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges). Esto puede requerir agregar FQDN a la lista de permitidos salientes en la configuración de su infraestructura de proxy o firewall: \* ** \*. API.Skype.com**, **. users.Storage.Live.com**y **Graph.Skype.com**. Para obtener instrucciones sobre cómo abrir estos puertos en su firewall, consulte la documentación que viene con él.
    
    Para obtener una lista de todos los puertos que necesita abrir, consulte [Office 365 URL e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).

9. Asegúrese de que el administrador de la organización también haya seguido estos pasos.
    
10. **AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Puede permitir a los usuarios que busquen a todos los que usen Skype, la aplicación de consumidor gratuita, y que se comuniquen con ellos con mensajería instantánea. Para obtener más información, consulte [permitir que los usuarios de Skype empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Probar y solucionar problemas
<a name="bk_preview"> </a>

 **El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**
  
Para probar su instalación, necesita un contacto en Skype Empresarial que no esté bloqueado por el firewall de su empresa.
  
1. Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.
    
2. En Skype Empresarial, busque su contacto en Skype Empresarial y envíe una solicitud para chatear.
    
    Si recibe un mensaje que indica que no se pudo enviar debido a la Directiva de la empresa, debe comprobar las [direcciones URL y los intervalos de direcciones IP de Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Pida a su contacto de Skype Empresarial que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).
    
4. Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contrato. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio
<a name="bk_preview"> </a>

Después de habilitar la comunicación externa con otros usuarios de Skype empresarial, los usuarios pueden buscar usuarios federados de Skype empresarial buscando su nombre de inicio de sesión: por ejemplo, Rob@contoso.com. Luego deben agregar a la persona a su lista de contactos.
  
![Para buscar un usuario en una empresa federada, debe buscar su dirección de correo electrónico (suele ser también su nombre de inicio de sesión).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Sugerencias para configurar las comunicaciones con empresas federadas
<a name="bk_preview"> </a>

- Para configurar la Federación entre Skype empresarial 2015 y Skype empresarial online, consulte este artículo: [configurar la Federación con Skype empresarial online](https://technet.microsoft.com/library/jj205126.aspx).
    
- Para configurar la Federación entre Lync y Skype empresarial online, consulte este artículo: [configuración de la compatibilidad de Federación para un cliente de Lync Online](https://technet.microsoft.com/library/hh202193.aspx).
    
- Cuando dos usuarios de Skype Empresarial en Office 365 se comunican entre sí en dominios distintos, solo pueden usar las características de Skype Empresarial (por ejemplo, conversaciones de vídeo o compartir escritorio) que estén activadas en las dos organizaciones.
    
- Si un usuario de Skype empresarial de su organización se coloca en una retención local o por juicio, cualquier conversación de mensajería instantánea entre ese usuario y otros usuarios de Skype empresarial o Skype se guardará en **los elementos recuperables** de su buzón. Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Desactivar la comunicación externa para personas específicas
<a name="bk_preview"> </a>

Después de habilitar la comunicación externa para toda su empresa, puede desactivarla para personas específicas solamente.
  
1. Inicie sesión con su cuenta de administrador de Office 365.
    
2. En el centro de administración, vaya **a** > usuarios**activos**.
    
3. En la lista de usuarios, elija el usuario y, a continuación, en **Más configuraciones**, haga clic en **Editar propiedades de Skype Empresarial**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. En el **centro de administración de Skype empresarial**, elija **comunicaciones externas**.
    
    En la página **Opciones** , se seleccionarán todas las opciones. Borre las comunicaciones que desea deshabilitar. En la siguiente imagen se muestra que Jakob podrá comunicarse con personas de otras empresas de confianza, pero no con otros usuarios de Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Elija **Guardar**.
    
> [!NOTE]
> Es posible que haya que esperar hasta 24 horas para que los cambios tengan efecto. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Temas relacionados
<a name="bk_preview"> </a>

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
