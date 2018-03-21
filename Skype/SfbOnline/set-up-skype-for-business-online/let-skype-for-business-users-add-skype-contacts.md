---
title: Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: 961fc75aec1c01cbee3199c4c576a42e2c626849
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype

Con Skype Empresarial, los usuarios pueden buscar a todos los que usen la aplicación gratuita de Skype (la aplicación gratuita) y comunicarse con ellos con mensajería instantánea. En este artículo se explica lo que necesita hacer para que puedan agregar contactos de Skype. 
  
Debe tener [Acerca de los roles de administrador de Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) en Office 365 para realizar esta acción.
  
1. Inicie sesión con su cuenta de administrador de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. En **Centro de administración de Skype Empresarial**, seleccione **organización** > **comunicaciones externas**. 
    
4. De forma predeterminada, sus usuarios se pueden comunicar con el resto de personas del mundo que usen Skype Empresarial (siempre que su firewall se haya configurado para permitirlo). 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Si desea que sus usuarios chateen con usuarios de Skype, PERO no quiere que chateen con otras personas que usen Skype Empresarial, seleccione **Activado solo para los dominios permitidos**. Cuando habilita el contacto con los usuarios de Skype, skype.com se agrega automáticamente como un dominio permitido en segundo plano. 
    
    Si desea permitir el contacto a todas las empresas del mundo que utilicen Skype Empresarial, salvo a unas concretas, seleccione **Activado excepto para los dominios bloqueados** y seleccione **+** para agregar estos dominios. Todos podrán contactar con usted a excepción de las personas que se encuentren en esos dominios concretos. (Algunas empresas podrían necesitar seleccionar esta opción si, por ejemplo, tienen un litigio con otra empresa y deben cerciorarse de que no hay ningún contacto con otra empresa).
    
5. Seleccione **Permitir que las personas utilicen Skype Empresarial para comunicarse con usuarios de Skype fuera de la organización**. 
    
6.  Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.
    
    Si su organización usa otra solución para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a todas las [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para la conectividad de Skype y la búsqueda del directorio de Skype. Esto puede requerir agregar estas direcciones a la lista de permitidos de salida en la configuración de infraestructura de proxy o firewall.
    
7. **AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.
    
8. Muestre a los usuarios cómo encontrar y agregar contactos de Skype a la lista de contactos de Skype Empresarial. Pídales que lean [Buscar contactos en Skype Empresarial](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Probar y solucionar problemas

Para probar su instalación, necesita un contacto en Skype que no esté bloqueado por el firewall de su empresa. Esta persona tendría que haber iniciado sesión en Skype con una cuenta de Gmail, Outlook.com u otro tipo de cuenta de correo electrónico.
  
1. Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.
    
2. Cierre la sesión en Skype Empresarial y después vuelva a iniciarla para que pueda ver la opción de buscar en el directorio de Skype. 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. En Skype Empresarial, busque su contacto en Skype y envíe una solicitud para chatear. 
    
    Si se le indica que no se pudo enviar el mensaje debido a la directiva de la empresa, tendrá que volver a comprobar su [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contacto de Skype. 
    
  - **Si ha enviado a su contacto de Skype una solicitud y nunca la recibe**, pídale que le envíe una solicitud para chatear. Si el problema se producía al establecer una conexión entre Skype y Skype Empresarial, esto suele solucionarlo.
    
  - Ahora, si el mensaje se envía en la cafetería, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Lo que se puede hacer y lo que no

- **Skype Empresarialpara Mac** no permite buscar contactos de Skype ni comunicarse con ellos.
    
- Si bien usted puede buscar y encontrar usuarios de Skype, ellos no pueden buscar y encontrar usuarios de Skype Empresarial. Debe enviarles una solicitud de contacto, y ellos deben ingresar a Skype y aceptarla antes de que usted pueda enviarles mensajes instantáneos (IM). 
    
- No es posible permitir la conectividad de mensajería instantánea con otros proveedores de mensajería instantánea como Google o Facebook. No puede utilizar Skype Empresarial para enviar mensajes de texto a teléfonos móviles.

- ¿Cuáles son las características disponibles al agregar contactos de Skype?
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Los contactos de Skype que hayan iniciado sesión con su cuenta Microsoft (anteriormente, Windows Live ID) podrán obtener algunas características (pero no todas ellas) cuando se comuniquen con sus usuarios de Skype Empresarial.

Los contactos de Skype que inicien sesión con su cuenta de Microsoft (anteriormente de Windows Live ID) podrán disfrutar de algunas de las características (aunque no todas) cuando hablen con sus usuarios de Skype Empresarial.
  
|**No disponible con los contactos de Skype**|**No disponible con los contactos de Skype**|
|:-----|:-----|
| Conversaciones de vídeo <br/>  Mensajería instantánea de persona a persona <br/>  Presencia <br/> | Conversaciones de MI con varios participantes <br/>  Conversaciones de audio y vídeo con tres o más personas <br/>  Uso compartido de escritorio y programas <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>See also

[Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

## <a name="feedback"></a>¿Comentarios?
Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).