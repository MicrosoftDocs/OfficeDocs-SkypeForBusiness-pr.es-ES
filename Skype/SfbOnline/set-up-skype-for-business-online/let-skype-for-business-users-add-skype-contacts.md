---
title: Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: afe1cb7f465a2a2e43056d01e7512f6f46c0f587
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494163"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype

Con Skype Empresarial, los usuarios pueden buscar a todos los que usen la aplicación gratuita de Skype (la aplicación gratuita) y comunicarse con ellos con mensajería instantánea. En este artículo se explica lo que necesita hacer para que puedan agregar contactos de Skype. 
  
Para ello, debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) en Office 365.

![Un icono que muestra el logotipo](../images/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**
  
1. Inicie sesión con su cuenta de administrador de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. En Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. En el **centro de administración de Skype empresarial**, elija**comunicaciones externas**de la **organización** > . 
    
4. De forma predeterminada, sus usuarios se pueden comunicar con el resto de personas del mundo que usen Skype Empresarial (siempre que su firewall se haya configurado para permitirlo). 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Si desea que sus usuarios chateen con usuarios de Skype, PERO no quiere que chateen con otras personas que usen Skype Empresarial, seleccione **Activado solo para los dominios permitidos**. Cuando habilita el contacto con los usuarios de Skype, skype.com se agrega automáticamente como un dominio permitido en segundo plano. 
    
    Si desea permitir el contacto a todas las empresas del mundo que utilicen Skype Empresarial, salvo a unas concretas, seleccione **Activado excepto para los dominios bloqueados** y seleccione **+** para agregar estos dominios. Todos podrán contactar con usted a excepción de las personas que se encuentren en esos dominios concretos. (Algunas empresas podrían necesitar seleccionar esta opción si, por ejemplo, tienen un litigio con otra empresa y deben cerciorarse de que no hay ningún contacto con otra empresa).
    
5. Seleccione **Permitir que las personas utilicen Skype Empresarial para comunicarse con usuarios de Skype fuera de la organización**. 
    
6.  Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.
    
    Si su organización usa otra solución para impedir que los equipos de su red se conecten a Internet, asegúrese de que los equipos cliente pueden acceder a todas las [direcciones IP y direcciones URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para conectividad de Skype y búsqueda en el directorio de Skype. Esto puede requerir agregar estas direcciones a la lista de permitidos de salida en la configuración de infraestructura de proxy o firewall.
    
7. **AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cada vez que modifica la configuración de comunicaciones externas, los cambios pueden demorar hasta 24 horas en completarse en todos los centros de datos.
    
8. Muestre a los usuarios cómo encontrar y agregar contactos de Skype a la lista de contactos de Skype Empresarial. Pídales que lean [Buscar contactos en Skype Empresarial](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Probar y solucionar problemas

Para probar su instalación, necesita un contacto en Skype que no esté bloqueado por el firewall de su empresa. Esta persona tendría que haber iniciado sesión en Skype con una cuenta de Gmail, Outlook.com u otro tipo de cuenta de correo electrónico.
  
1. Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.
    
2. Cierre la sesión en Skype Empresarial y después vuelva a iniciarla para que pueda ver la opción de buscar en el directorio de Skype. 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. En Skype Empresarial, busque su contacto en Skype y envíe una solicitud para chatear. 
    
    Si recibes el mensaje no se pudo enviar debido a la Directiva de la empresa, deberás comprobar la [configuración del firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Skype Empresarial para enviar una solicitud para chatear a su contacto de Skype. 
    
   - **Si ha enviado a su contacto de Skype una solicitud y nunca la recibe**, pídale que le envíe una solicitud para chatear. Si el problema se producía al establecer una conexión entre Skype y Skype Empresarial, esto suele solucionarlo.
    
   - Ahora, si el mensaje se envía en la cafetería, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Lo que se puede hacer y lo que no

- **Skype Empresarialpara Mac** no permite buscar contactos de Skype ni comunicarse con ellos.
    
- Cuando la búsqueda de directorio está habilitada, puede buscar y buscar usuarios de Skype y Skype empresarial. Si, por algún motivo, no puedes encontrarlos en el directorio, puedes enviarles una solicitud de autorización y, después, pedirles que inicien sesión en Skype y que lo acepten para que puedas enviar mensajes instantáneos con ellos. 
    
- No es posible permitir la conectividad de mensajería instantánea con otros proveedores de mensajería instantánea como Google o Facebook. No puede utilizar Skype Empresarial para enviar mensajes de texto a teléfonos móviles.

- No es posible grabar llamadas de audio o vídeo entre un contacto de Skype y un contacto de Skype empresarial.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>¿Cuáles son las características disponibles al agregar contactos de Skype?

Los contactos de Skype que hayan iniciado sesión con su cuenta Microsoft (anteriormente, Windows Live ID) pueden obtener algunas de las características, pero no todas, cuando se comuniquen con los usuarios de Skype empresarial.
  
|**Disponible con los contactos de Skype**|**No disponible con los contactos de Skype**|
|:-----|:-----|
| Conversaciones de vídeo <br/>  Mensajería instantánea de persona a persona <br/>  Presencia <br/> | Conversaciones de MI con varios participantes <br/>  Conversaciones de audio y vídeo con tres o más personas <br/>  Uso compartido de escritorio y programas <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Temas relacionados

[Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

  
 
