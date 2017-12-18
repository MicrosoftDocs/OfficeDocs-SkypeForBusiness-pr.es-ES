---
title: "Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460

description: "See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. "
---

# Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Con Skype Empresarial, los usuarios pueden buscar a todos los que usen la aplicación gratuita de Skype (la aplicación gratuita) y comunicarse con ellos con mensajería instantánea. En este artículo se explica lo que necesita hacer para que puedan agregar contactos de Skype. 
  
Debe tener [Acerca de los roles de administrador de Office 365](about-office-365-admin-roles.md) en Office 365 para realizar esta acción.
  
1. Inicie sesión con su cuenta de administrador de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. En el **Centro de administración de Skype Empresarial**, elija **organización** > **comunicaciones externas**.
    
4. De forma predeterminada, sus usuarios se pueden comunicar con el resto de personas del mundo que usen Skype Empresarial (siempre que su firewall se haya configurado para permitirlo). 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Si desea que sus usuarios chateen con usuarios de Skype, PERO no quiere que chateen con otras personas que usen Skype Empresarial, seleccione **Activado solo para los dominios permitidos**. Cuando habilita el contacto con los usuarios de Skype, skype.com se agrega automáticamente como un dominio permitido en segundo plano. 
    
    Si desea permitir el contacto a todas las empresas del mundo que utilicen Skype Empresarial, salvo a unas concretas, seleccione **Activado excepto para los dominios bloqueados** y seleccione **+** para agregar estos dominios. Todos podrán contactar con usted a excepción de las personas que se encuentren en esos dominios concretos. (Algunas empresas podrían necesitar seleccionar esta opción si, por ejemplo, tienen un litigio con otra empresa y deben cerciorarse de que no hay ningún contacto con otra empresa).
    
5. Seleccione **Permitir que las personas utilicen Skype Empresarial para comunicarse con usuarios de Skype fuera de la organización**. 
    
6. Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados. 
    
    Si su organización usa otra solución para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a todas las [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx) para la conectividad de Skype y la búsqueda del directorio de Skype. Esto puede requerir agregar estas direcciones a la lista de permitidos de salida en la configuración de infraestructura de proxy o firewall.
    
7. **AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.
    
8. Muestre a los usuarios cómo encontrar y agregar contactos de Skype a la lista de contactos de Skype Empresarial. Pídales que lean [Buscar contactos en Skype Empresarial](http://technet.microsoft.com/library/b12500ef-e37f-4d22-aade-c11277e53f19%28Office.14%29.aspx).
    
## Probar y solucionar problemas

Para probar su instalación, necesita un contacto en Skype que no esté bloqueado por el firewall de su empresa. Esta persona tendría que haber iniciado sesión en Skype con una cuenta de Gmail, Outlook.com u otro tipo de cuenta de correo electrónico.
  
1. Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.
    
2. Cierre la sesión en Skype Empresarial y después vuelva a iniciarla para que pueda ver la opción de buscar en el directorio de Skype. 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. En Skype Empresarial, busque su contacto en Skype y envíe una solicitud para chatear. 
    
    Si se le indica que no se pudo enviar el mensaje debido a la directiva de la empresa, tendrá que volver a comprobar su [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx). 
    
4. Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contacto de Skype. 
    
  - **Si ha enviado a su contacto de Skype una solicitud y nunca la recibe**, pídale que le envíe una solicitud para chatear. Si el problema se producía al establecer una conexión entre Skype y Skype Empresarial, esto suele solucionarlo.
    
  - Ahora, si el mensaje se envía en la cafetería, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall. 
    
## Lo que se puede hacer y lo que no

- **Skype Empresarialpara Mac** no permite buscar contactos de Skype ni comunicarse con ellos.
    
- Mientras que puede buscar y encontrar los usuarios de Skype, que no pueden buscar y encontrar usuarios Skype Empresarial. Tiene que le envíe una solicitud de contacto y tienen que iniciar sesión en Skype y aceptarlo antes de poder mensajería instantánea con ellos.
    
- No es posible permitir la conectividad de mensajería instantánea con otros proveedores de mensajería instantánea como Google o Facebook. No puede utilizar Skype Empresarial para enviar mensajes de texto a teléfonos móviles.
    
## ¿Cuáles son las características disponibles al agregar contactos de Skype?

contactos de Skype que ha iniciado sesión con su cuenta de Microsoft (anteriormente, Windows Live ID) para obtener algunos, pero no para todas las características cuando están hablando con los usuarios de Skype Empresarial.
  
|**Disponible con los contactos de Skype**|**No disponible con los contactos de Skype**|
|:-----|:-----|
| Conversaciones de vídeo <br/>  Mensajería instantánea de persona a persona <br/>  Presencia <br/> | Conversaciones de MI con varios participantes <br/>  Conversaciones de audio y vídeo con tres o más personas <br/>  Uso compartido de escritorio y programas <br/> |
   
## 

 *Última actualización: 23 de marzo de 2017* 
  
||
|:-----|
|![Icono pequeño de LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **¿Usa Office 365 por primera vez?**         Descubra cursos en vídeo gratuitos para **administradores de Office 365 y profesionales de TI**, ofrecidos por LinkedIn Learning. |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

