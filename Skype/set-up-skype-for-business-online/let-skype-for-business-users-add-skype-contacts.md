---
title: Permitir Skype para usuarios de negocios agregar contactos de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Consulte cómo permitir que las personas que utilizan Skype para el contacto profesional Skype para usuarios empresariales desde fuera de su organización y agregan a su lista de contactos. "
ms.openlocfilehash: 1add1f6e907613d1ac536c92b57cfce7f3cdaf66
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Permitir Skype para usuarios de negocios agregar contactos de Skype

Con Skype para el negocio, los usuarios pueden buscar y mensajes Instantáneos con cualquier persona que utilice Skype, la aplicación gratuita! Este artículo explica lo que debe hacer para que pueden agregar contactos de Skype. 
  
Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) en Office 365 para ello.
  
1. Inicie sesión con su cuenta de administración de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. En el centro de administración de Office 365, vaya a **Centros de Admin** > **Skype para el negocio**. 
    
    ![Elija el Skype para el centro de administración de negocios.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. En el **Skype para el centro de administración de negocios**, seleccione **organización** > **comunicaciones externas**. 
    
4. De forma predeterminada, los usuarios pueden comunicarse con todas las otras personas en el mundo que utilizan Skype para empresas (suponiendo que el firewall se ha configurado para ello). 
    
    ![Elija permitirme personas utilizan Skype para empresas para comunicarse con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Si desea que los usuarios de charla con usuarios de Skype, pero no desea charlar con otras personas que utilizan Skype para el negocio, elija **sólo permiten dominios**. Cuando se habilita el contacto con los usuarios de Skype, skype.com se agrega automáticamente como un dominio permitido entre bastidores. 
    
    Si desea permitir el contacto de todos los otros negocios del mundo mediante Skype para el negocio, excepto en algunos específicos, elija **en excepto dominios bloqueados**y seleccione **+** para agregar esos dominios. Todos los usuarios podrán ponerse en contacto con usted excepto los usuarios de esos dominios específicos. (Algunas empresas pueden elegir esta opción, por ejemplo, si se encuentran en litigios y necesite asegurarse de no hay ningún contacto con el otro negocio).
    
5. Elija **permiten a los usuarios utilizar Skype para empresas para comunicarse con usuarios de Skype fuera de su organización**. 
    
6.  Si utiliza Firewall de Windows, Skype para empresas abre los puertos necesarios automáticamente.
    
    Si su organización utiliza otra solución para impedir que los equipos de la red conecta a Internet, asegúrese de que los equipos cliente tienen acceso a todas las [direcciones URL y direcciones IP](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para la conectividad de Skype y Skype Directory Search. Esto puede requerir agregándolos a la salida lista de admitidos en la configuración de infraestructura de firewall o proxy.
    
7. **Esperar hasta 24 horas para probar**. Cada vez que cambie la configuración de comunicaciones externas, puede tardar hasta 24 horas para que los cambios rellenar a través de todos los centros de datos.
    
8. Enseñe a los usuarios buscar y agregar contactos de Skype a su lista de Skype para contactos profesionales. Remítales a [Buscar personas en Skype para el negocio](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Probar y solucionar problemas

Para probar la configuración, es necesario un contacto en Skype que no está detrás de su firewall de la compañía. Puede iniciar sesión en Skype con una cuenta de Gmail, Outlook.com cuenta u otro tipo de cuenta de correo electrónico.
  
1. Después de cambiar la configuración de comunicaciones externas, **esperar hasta 24 horas a prueba**.
    
2. Cerrar la sesión de Skype para el negocio y, a continuación, iniciar sesión de nuevo para ver la opción de buscar en el directorio de Skype. 
    
    ![Cuando esté resaltado el directorio Skype, puede buscar personas que tengan cuentas de Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. En Skype para el negocio, buscar el contacto en Skype y enviar una solicitud de charla. 
    
    Si recibe el mensaje que se no se ha podido enviar debido a la directiva de empresa, debe comprobar la [Configuración del firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Póngase en contacto con la otra forma de comprobar si el problema es el servidor de seguridad es ir a una ubicación de wifi no detrás del servidor de seguridad como una cafetería y usar Skype para empresas para enviar una solicitud a su Skype para charlar. 
    
  - **Si ha enviado su contacto de Skype una solicitud y que nunca ha llegado**, pídale que envíe una solicitud de charla. Si el problema era establecer una conexión entre Skype y Skype para el negocio, a menudo resuelve.
    
  - Ahora si el mensaje pasa por en la cafetería, pero no cuando está en el trabajo, entonces usted sabe el problema es el servidor de seguridad. 
    
## <a name="what-you-can-and-cant-do"></a>Lo que puede y no puede hacer

- **Skype para el negocio en Mac** no tiene la capacidad de buscar y comunicarse con los contactos de Skype.
    
- Mientras que puede buscar y buscar usuarios de Skype, ellos no se pueden buscar y encontrar Skype para usuarios profesionales. Tienes que enviarles una solicitud de contacto, y tienen que iniciar sesión en Skype y aceptarla para poder IM con ellos. 
    
- No es posible permitir la conectividad de mensajería instantánea con otros proveedores de mensajería instantánea como Google o Facebook. No puede utilizar Skype para empresas para enviar mensajes de texto de teléfono celular.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>¿Qué funciones están disponibles al agregar contactos de Skype?

Contactos de Skype que has iniciado sesión con su cuenta de Microsoft (anteriormente Windows Live ID) pueden obtener algunos, pero no todas, las características cuando están hablando con su Skype para usuarios de negocios.
  
|**Disponible con contactos de Skype**|**No disponible con contactos de Skype**|
|:-----|:-----|
| Conversaciones de vídeo <br/>  Mensajería instantánea persona-a-persona <br/>  Presence <br/> | Conversaciones de mensajería instantánea con varios usuarios <br/>  Conversaciones de audio y vídeo con tres o más personas <br/>  Escritorio y uso compartido de programas <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Temas relacionados

[Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
