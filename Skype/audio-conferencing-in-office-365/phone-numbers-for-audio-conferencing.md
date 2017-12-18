---
title: "Números de teléfono para las conferencias de Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7

description: "Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned."
---

# Números de teléfono para las conferencias de Audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Al configurar ** Conferencias de Audio** de Skype para la empresa y Teams de Microsoft, números de teléfono se asignan automáticamente a su organización. Puede ver los números de teléfono asignados a su puente de conferencia de audio, vaya a la **Skype centro de administración de negocio** > **audioconferencia** > **puente de Microsoft**. Vea [Ver una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> No hay un recurso que contiene una lista de todos los números de acceso telefónico para conferencias de Audio. Si está buscando para ver si hay números de teléfono disponibles en su área o país o región, utilice el **Skype centro de administración de negocio** > **voz** > **Números de teléfono**, haga clic en **Agregar** **Nuevos números de servicio**. Utilice las listas de **País o región**, estado o la región de y **Ciudad** para filtrar la búsqueda.> Además, si está buscando números de servicio gratuito de pago, seleccione **número gratuito** desde el **estado o la región** lista.
  
## Cobertura de conferencias de audio y precios

Para obtener una lista completa de todos los países o regiones y ciudades donde hay conferencias de Audio, vea [¿Las conferencias RTC con números de teléfono están disponibles en mi país o región?](http://technet.microsoft.com/library/1096d81e-7e14-488c-95d8-b8322e39c059%28Office.14%29.aspx).
  
[Precios para conferencias de Audio](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## Números de teléfono de acceso telefónico local en la invitación a la reunión

Cuando un Skype empresarial Online o Microsoft Teams usuario programa una reunión en Outlook o Outlook Web App, el número de conferencia de audio predeterminado establecido para el usuario se incluye en la invitación a la reunión. Si desea seleccionar un número predeterminado diferente para uno o más usuarios, que puede cambiar, vaya a la **Skype centro de administración de empresas** > **audioconferencia** > **usuarios**. Consulte [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
Para ver otros números de acceso telefónico local, haga clic en el vínculo **Buscar un número local** en la invitación a la reunión.
  
## Establecer en un puente de conferencia de audio de números de teléfono

Existen dos tipos de números de teléfono de conferencias de audio que se pueden asignar a su puente de conferencia: **Shared** y **dedicado**. Ambos tipos de estos números pueden usarse por cualquier llamador para unirse a reuniones de audio que se mantienen en su organización.
  
 **Dedicado a números de teléfono** son los números de teléfono que solo están disponibles para los usuarios de su organización. Puede cambiar los idiomas que se usan cuando alguien le llama uno de estos números.
  
 **Números de teléfono de compartido** son los números de teléfono que pueden compartir con otras organizaciones de Office 365. No puede cambiar los idiomas que se usan cuando alguien le llama uno de estos números.
  
Mientras que el número de conferencia de audio predeterminado que se ha asignado a un organizador solo se incluye en la invitación a la reunión, un llamador puede utilizar cualquiera de los números de teléfono que se asignan a su puente de conferencia para unirse a una reunión. La lista de números de teléfono que pueden utilizarse para unirse a una reunión está disponible mediante el vínculo **Buscar un número local** que se incluye en cada invitación a la reunión.
  
## Le asigna automáticamente a los números de teléfono de conferencias de audio

Compartir teléfono audioconferencia números se asignan automáticamente a las organizaciones cuando están habilitados para conferencias de audio. Cuando se asignan los números de teléfono, se asigna un número de teléfono como el número de teléfono predeterminado del puente de conferencia. El número de teléfono asignado como el número predeterminado del puente será una desde el país o región de la organización.
  
> [!NOTE]
> La ubicación de país o región de su organización puede encontrarse al iniciar sesión en el **Centro de administración de Office 365** y buscar en el **Perfil de la organización**. 
  
> [!CAUTION]
> Debido a la disponibilidad limitada de números de teléfono de pago en Venezuela, Indonesia y Emiratos Árabes Unidos (Emiratos), las organizaciones de estos países o regiones no tiene un número de pago de conferencias de Audio se asigna automáticamente a ellos. Números de teléfono gratuitos desde estas ubicaciones están disponibles en función de inventario disponible. 
  
Números de teléfono de conferencias de audio dedicada son números de servicio que puede obtener y, a continuación, asignar a su organización. Números de servicio pueden encontrarse mediante la **Skype centro de administración de la empresa**. Para obtener más información, consulte [Obtener números de teléfono de servicio de Skype Empresarial](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md).
  
Para ver una lista de las países o regiones que tienen números de teléfono que se asigna automáticamente a las organizaciones, vea [Países y disponibilidad de la región para llamar a los planes y las conferencias de Audio](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## ¿Qué más tengo que saber?

- Para ver la lista de los idiomas admitidos para conferencias de audio, vea [Audioconferencia idiomas compatibles](audio-conferencing-supported-languages.md).
    
- Puede usar el cmdlet [Get-cmdlets CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) para ver los números de teléfono dedicada para conferencias de audio para su organización.
    
- Puede usar el cmdlet [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) para ver los idiomas que se pueden establecer en un número de teléfono de acceso telefónico dedicado.
    
- Puede configurar hasta 4 idiomas para cada número de teléfono de conferencias de audio: uno principal y tres secundarios. Y también puede establecer idiomas en un número de teléfono de conferencias de audio dedicada.
    
- Para establecer el número de teléfono de acceso telefónico para un usuario, vea [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
    
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

[Conferencias de acceso telefónico en Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

