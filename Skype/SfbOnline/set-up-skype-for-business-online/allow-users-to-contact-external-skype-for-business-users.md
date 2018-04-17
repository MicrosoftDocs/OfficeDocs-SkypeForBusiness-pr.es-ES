---
title: Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: b7700eeaf9a2fdd39d9a25fce93cfd17f42d4b8e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial

> [!NOTE]
> Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations. 
  
Siga los pasos de este artículo cuando:
  
- Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.
    
- Desee que las personas de su empresa puedan usar Skype Empresarial para ponerse en contacto con personas de empresas específicas de fuera de su organización.
    
-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address. Esto funcionará automáticamente si usted y el otro usuario usan la configuración predeterminada de Skype Empresarial. De lo contrario, deben asegurarse de que la configuración no esté bloqueando su dominio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicaciones entre empresas para los usuarios
<a name="bk_preview"> </a>

To see how this works, watch this video:
***
> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=492278f0-6912-47ba-a1d1-00040061cf44&AutoPlayVideo=false]
***

You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.
  
1. Sign in with your Office 365 admin account. 
    
2. En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. En **Centro de administración de Skype Empresarial**, seleccione **organización** > **comunicaciones externas**.
    
4. To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.
    
    O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.
    
5. Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.
    
6. Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**. Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.
    
7. Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.
    
    Si su organización usa una solución de firewall diferente para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a los siguientes [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges). This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.
    
    For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).

8. Make sure that the administrator in the organization has also followed these steps.
    
9. **AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Puede permitir a los usuarios que busquen a todos los que usen Skype, la aplicación de consumidor gratuita, y que se comuniquen con ellos con mensajería instantánea. To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Probar y solucionar problemas
<a name="bk_preview"> </a>

 **El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**
  
Para probar su instalación, necesita un contacto en Skype Empresarial que no esté bloqueado por el firewall de su empresa.
  
1. Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.
    
2. En Skype Empresarial, busque su contacto en Skype Empresarial y envíe una solicitud para chatear.
    
    If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Pida a su contacto de Skype Empresarial que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).
    
4. Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contrato. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio
<a name="bk_preview"> </a>

After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.
  
![To find a user in a federated business, you must search for their email address (this is usually also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Sugerencias para configurar las comunicaciones con empresas federadas
<a name="bk_preview"> </a>

- Para configurar la federación entre Skype Empresarial 2015 y Skype Empresarial Online, consulte este artículo de Technet: [Configurar la federación con Skype Empresarial Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Para configurar la federación entre Lync y Skype Empresarial Online, consulte este artículo de Technet: [Configuración de la compatibilidad de federación para un cliente de Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Cuando dos usuarios de Skype Empresarial en Office 365 se comunican entre sí en dominios distintos, solo pueden usar las características de Skype Empresarial (por ejemplo, conversaciones de vídeo o compartir escritorio) que estén activadas en las dos organizaciones.
    
- If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox. Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Desactivar la comunicación externa para personas específicas
<a name="bk_preview"> </a>

Después de habilitar la comunicación externa para toda su empresa, puede desactivarla para personas específicas solamente.
  
1. Sign in with your Office 365 admin account.
    
2. In the Office 365 admin center, go to **Users** > **Active users**.
    
3. En la lista de usuarios, elija el usuario y, a continuación, en **Más configuraciones**, haga clic en **Editar propiedades de Skype Empresarial**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. In the **Skype for Business admin center**, choose **External communications**.
    
    On the **Options** page, all of the choices will be selected. Clear the communications you want to disable. En la siguiente imagen se muestra que Jakob podrá comunicarse con personas de otras empresas de confianza, pero no con otros usuarios de Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Elija **Guardar**.
    
> [!NOTE]
> Es posible que haya que esperar hasta 24 horas para que los cambios tengan efecto. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Temas relacionados
<a name="bk_preview"> </a>

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
