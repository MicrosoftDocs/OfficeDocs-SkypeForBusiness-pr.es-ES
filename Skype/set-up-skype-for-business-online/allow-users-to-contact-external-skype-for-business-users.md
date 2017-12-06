---
title: "Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
- Adm_UI_Elements
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94

description: "See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. "
---

# Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](b414873a-0059-4cd5-aea1-e5d0857dbc94.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/b414873a-0059-4cd5-aea1-e5d0857dbc94). 
  
> [!NOTE]
> Skype para la federación de empresa no está disponible para Office 365 ofrecido por 21Vianet y organizaciones de Office 365 Alemania. 
  
Siga los pasos de este artículo cuando: 
  
- Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.
    
- Desee que las personas de su empresa puedan usar Skype Empresarial para ponerse en contacto con personas de empresas específicas de fuera de su organización.
    
- O BIEN desea que el resto del mundo que usa Skype Empresarial pueda encontrarle y comunicarse con usted mediante su dirección de correo electrónico. Esto funcionará automáticamente si usted y el otro usuario usan la configuración predeterminada de Skype Empresarial. De lo contrario, deben asegurarse de que la configuración no esté bloqueando su dominio.
    
## Habilitar comunicaciones entre empresas para los usuarios
<a name="bk_preview"> </a>

Debe tener [Acerca de los roles de administrador de Office 365](about-office-365-admin-roles.md) en Office 365 para realizar esta acción.
  
1. Inicie sesión con su cuenta de administrador de Office 365.
    
2. En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. En el **Centro de administración de Skype Empresarial**, elija **organización** > **comunicaciones externas**.
    
4. Para configurar la comunicación con una empresa específica o con los usuarios de otro dominio, en el cuadro de lista desplegable, elija **Activar solo para dominios permitidos**.
    
    O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.
    
5. En **dominios bloqueados o permitidos**, elija **+** y agregue el nombre del dominio que desea permitir.
    
6. Asegúrese de que el Administrador de la otra organización tiene los mismos pasos en sus **Centro de administración de Skype Empresarial**. Por ejemplo, en su lista de **dominios permitidos**, su administrador debe introducir el dominio para su empresa.
    
7. Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados. 
    
    Si su organización usa una solución de otro firewall para restringir los equipos de la red de la conexión a Internet, asegúrese de que los equipos cliente están teniendo acceso a los siguientes [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx). Esto puede requerir agregar el FQDN a la salida permiten la lista en el servidor proxy o firewall configuración de infraestructura: ***. api.skype.com, *. users.storage.live.com y graph.skype.com**. Para obtener instrucciones sobre cómo abrir estos puertos en el firewall, consulte la documentación incluida con él.
    
    Para obtener una lista de todos los puertos que debe abrir, consulte [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx#bkmk_lyo) en el artículo de la[URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx).
    
8. **Esperar hasta 24 horas para probar**. Cada vez que cambie la configuración de comunicaciones externas, puede tardar hasta 24 horas para que los cambios rellenar a través de todos los centros de datos.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Puede permitir que a los usuarios a buscar y la mensajería instantánea con todos los usuarios de Skype, la aplicación gratuita consumidor! Para obtener más información, vea[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## Probar y solucionar problemas
<a name="bk_preview"> </a>

 **El problema más común personas pueden encontrarse al configurar la comunicación entre empresas está recibiendo sus [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx) derecha.**
  
Para probar la instalación, es necesario un contacto en Skype Empresarial que no se encuentra detrás del firewall de la compañía.
  
1. Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.
    
2. En Skype Empresarial, busque su contacto en Skype Empresarial y envíe una solicitud para chatear. 
    
    Si recibe un mensaje de no pudo enviarse debido a la directiva de empresa, debe seleccione la [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx).
    
3. Pida a su contacto de Skype Empresarial que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta). 
    
4. Otra manera de comprobar si el problema es el firewall es ir a una ubicación de Wi-Fi no detrás de su servidor de seguridad como una cafetería y usar Skype Empresarial para enviar una solicitud a su contacto para conversar. Si el mensaje se pasa por allí, pero no cuando está en el trabajo, a continuación, sabrá que el problema es el firewall.
    
## Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio
<a name="bk_preview"> </a>

Después de habilitar las comunicaciones externas con otros usuarios de Skype Empresarial, los usuarios puedan encontrar los usuarios federados Skype Empresarial buscando su nombre de inicio de sesión: por ejemplo, Rob@contoso.com. A continuación, tendrá que agregue a la persona a su lista de contactos.
  
![To find a user in a federated business, you must search for their email address (this is usally also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## Sugerencias para configurar las comunicaciones con empresas federadas
<a name="bk_preview"> </a>

- Para configurar la federación entre Skype Empresarial 2015 y Skype Empresarial Online, consulte este artículo de Technet: [Configurar la federación con Skype Empresarial Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Para configurar la federación entre Lync y Skype Empresarial Online, consulte este artículo de Technet: [Configuración de la compatibilidad de federación para un cliente de Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Cuando dos usuarios de Skype Empresarial en Office 365 se comunican entre sí en dominios distintos, solo pueden usar las características de Skype Empresarial (por ejemplo, conversaciones de vídeo o compartir escritorio) que estén activadas en las dos organizaciones. 
    
- Si un usuario Skype Empresarial en su organización se coloca en un local o mantenga litigios, se guardan las conversaciones de mensajería instantánea entre ese usuario y otros Skype Empresarial o los usuarios de Skype en **Elementos recuperables** en su buzón. Estas conversaciones no se guardan en la carpeta **Historial de conversaciones** en su buzón.
    
## Desactivar la comunicación externa para personas específicas
<a name="bk_preview"> </a>

Después de habilitar la comunicación externa para toda su empresa, puede desactivarla para personas específicas solamente. 
  
1. Inicie sesión con su cuenta de administrador de Office 365.
    
2. En la Centro de administración de Office 365, vaya a **usuarios** > **usuarios activos**.
    
3. En la lista de usuarios, elija el usuario y, a continuación, en **Más configuraciones**, haga clic en **Editar propiedades de Skype Empresarial**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. En la **Skype centro de administración de empresa**, elija **comunicaciones externas**.
    
    En la página de **Opciones**, se selecciona todas las opciones. Desactive las comunicaciones que desee deshabilitar. La imagen siguiente muestra que Jakob podrán comunicarse con personas de otras empresas de confianza, pero no con otros usuarios de Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Elija **Guardar**.
    
> [!NOTE]
> Es posible que haya que esperar hasta 24 horas para que los cambios tengan efecto. 
  
## 
<a name="bk_preview"> </a>

 *Última actualización del artículo: 23 de marzo de 2017* 
  
## 
<a name="bk_preview"> </a>

||
|:-----|
|![Icono pequeño de LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **¿Usa Office 365 por primera vez?**         Descubra cursos en vídeo gratuitos para **administradores de Office 365 y profesionales de TI**, ofrecidos por LinkedIn Learning. |
   
## Temas relacionados
<a name="bk_preview"> </a>

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

