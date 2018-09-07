---
title: Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
ms.openlocfilehash: 79ba0754178e3d638520c932e6288a92ddf6e857
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854705"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial

> [!NOTE]
> Skype para la federación de negocio no está disponible para Office 365 operado por 21Vianet y las organizaciones de Office 365 Alemania. 
  
Siga los pasos de este artículo cuando:
  
- Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.
    
- Desee que las personas de su empresa puedan usar Skype Empresarial para ponerse en contacto con personas de empresas específicas de fuera de su organización.
    
-Desea que cualquier persona en el mundo que usa Skype para la empresa que puedan buscar y ponerse en contacto con usted, utilizando su dirección de correo electrónico. Esto funcionará automáticamente si usted y el otro usuario usan la configuración predeterminada de Skype Empresarial. De lo contrario, deben asegurarse de que la configuración no esté bloqueando su dominio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicaciones entre empresas para los usuarios
<a name="bk_preview"> </a>

Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en Office 365 en ambas organizaciones para ello.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
  
1. Inicie sesión con su cuenta de administración de Office 365. 
    
2. En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. En **Centro de administración de Skype Empresarial**, seleccione **organización** > **comunicaciones externas**.
    
4. Para establecer la comunicación con un negocio específicos o con los usuarios en otro dominio, en el cuadro de lista desplegable, elija **sólo para permitido dominios**.
    
    O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.
    
5. En **dominios permitidos o bloqueados**, elija **+** y agregue el nombre del dominio que desea permitir.
    
6. Asegúrese de que el administrador en la otra organización estos mismos pasos en sus **Skype para el centro de administración de negocio**. Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.
    
7. Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.
    
    Si su organización usa una solución de firewall diferente para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a los siguientes [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges). Esto puede requerir la adición de los FQDN para la salida permiten lista en el firewall o el proxy la configuración de la infraestructura: ** \*. api.skype.com**, \* **. users.storage.live.com**y **graph.skype.com**. Para obtener instrucciones sobre cómo abrir estos puertos en el servidor de seguridad, consulte la documentación que lo acompaña.
    
    Para obtener una lista de todos los puertos que necesita abrir, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).

8. Asegúrese de que el Administrador de la organización también ha seguido estos pasos.
    
9. **AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Puede permitir a los usuarios que busquen a todos los que usen Skype, la aplicación de consumidor gratuita, y que se comuniquen con ellos con mensajería instantánea. Para obtener más información, vea [permiten Skype para usuarios profesionales agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Probar y solucionar problemas
<a name="bk_preview"> </a>

 **El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**
  
Para probar su instalación, necesita un contacto en Skype Empresarial que no esté bloqueado por el firewall de su empresa.
  
1. Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.
    
2. En Skype Empresarial, busque su contacto en Skype Empresarial y envíe una solicitud para chatear.
    
    Si recibe un mensaje que se han podido enviar debido a la directiva de empresa, debe comprobar su [URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Pida a su contacto de Skype Empresarial que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).
    
4. Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contrato. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio
<a name="bk_preview"> </a>

Después de habilitar las comunicaciones externas con otro Skype para usuarios profesionales, los usuarios puedan encontrar federada Skype para usuarios profesionales mediante la búsqueda de su nombre de inicio de sesión: por ejemplo, Rob@contoso.com. A continuación, deben agregar a la persona a su lista de contactos.
  
![Para buscar un usuario en una empresa federada, debe buscar su dirección de correo electrónico (Esto suele ser también su nombre de inicio de sesión).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Sugerencias para configurar las comunicaciones con empresas federadas
<a name="bk_preview"> </a>

- Para configurar la federación entre Skype para profesionales de 2015 y Skype para profesionales en línea, vea este artículo: [Configure la federación con Skype para profesionales en línea](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Para configurar la federación entre Lync y Skype para profesionales en línea, vea este artículo: [Configuración de la compatibilidad con la federación para un cliente de Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Cuando dos usuarios de Skype Empresarial en Office 365 se comunican entre sí en dominios distintos, solo pueden usar las características de Skype Empresarial (por ejemplo, conversaciones de vídeo o compartir escritorio) que estén activadas en las dos organizaciones.
    
- Si se pone un Skype para usuarios de empresa de la organización en un juicio o en contexto, se guardarán todas las conversaciones de mensajería instantánea entre ese usuario y otro Skype para los usuarios empresariales o de Skype en **Elementos recuperables** en su buzón. Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Desactivar la comunicación externa para personas específicas
<a name="bk_preview"> </a>

Después de habilitar la comunicación externa para toda su empresa, puede desactivarla para personas específicas solamente.
  
1. Inicie sesión con su cuenta de administración de Office 365.
    
2. En el centro de administración de Office 365, vaya a **los usuarios** > **usuarios activos**.
    
3. En la lista de usuarios, elija el usuario y, a continuación, en **Más configuraciones**, haga clic en **Editar propiedades de Skype Empresarial**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. En el **Skype para el centro de administración de negocio**, elija **comunicaciones externas**.
    
    En la página de **Opciones** , se seleccionarán todas las opciones. Desactive las comunicaciones que va a deshabilitar. En la siguiente imagen se muestra que Jakob podrá comunicarse con personas de otras empresas de confianza, pero no con otros usuarios de Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Elija **Guardar**.
    
> [!NOTE]
> Es posible que haya que esperar hasta 24 horas para que los cambios tengan efecto. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Temas relacionados
<a name="bk_preview"> </a>

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
