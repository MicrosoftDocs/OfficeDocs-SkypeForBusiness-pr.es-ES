---
title: "Obtener números de teléfono de servicio de Skype Empresarial"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734

description: "Además de obtener números de teléfono para usuarios individuales de Office 365, también es posible buscar y adquirir números de teléfono de pago o gratuitos para servicios como conferencias de acceso telefónico local (para puentes de conferencia) y operadores automáticos (conocidos como números de servicio). Los números de teléfono de servicio tienen una mayor capacidad de llamadas simultáneas que los números de teléfono de usuario o suscriptor. Por ejemplo, un número de servicio puede gestionar 100 llamadas simultáneas, mientras que un número de teléfono de usuario solo puede admitir unas pocas al mismo tiempo."
---

# Obtener números de teléfono de servicio de Skype Empresarial

Además de obtener números de teléfono para usuarios individuales de Office 365, también es posible buscar y adquirir números de teléfono de pago o gratuitos para servicios como conferencias de acceso telefónico local (para puentes de conferencia) y operadores automáticos (conocidos como números de servicio). Los números de teléfono de servicio tienen una mayor capacidad de llamadas simultáneas que los números de teléfono de usuario o suscriptor. Por ejemplo, un número de servicio puede gestionar 100 llamadas simultáneas, mientras que un número de teléfono de usuario solo puede admitir unas pocas al mismo tiempo.
  
> [!IMPORTANT]
> Debe configurarse primero el consumo RTC para poder adquirir números de teléfono gratuitos. 
  
Tiene dos maneras de obtener números de servicio para poder usarlos con Skype Empresarial: 
  
- Obtener números nuevos de Office 365 y Skype Empresarial.
    
- Realizar la portabilidad de los números existentes de su proveedor de servicios u operador telefónico o transferirlos.
    
    > [!NOTE]
    > Al transferir sus números de servicio, se recomienda enfáticamente que se ponga en contacto con el [Póngase en contacto con el soporte de Office 365 para empresas: ayuda para administradores](http://technet.microsoft.com/library/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b%28Office.14%29.aspx) para asegurarse de que se considere y configure correctamente una mayor capacidad de llamadas simultáneas.
  
## Obtener nuevos números de servicio

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la barra de navegación izquierda, vaya a **Voz** > **Números de teléfono** > **Agregar** y, a continuación, **Nuevos números de servicio**.
    
    **IMPORTANTE**: Para poder ver la opción **Voz** en el panel de navegación izquierdo del Centro de administración de Skype Empresarial, primero tiene que adquirir como mínimo una **licencia de Enterprise E5**, una licencia del complemento **Sistema telefónico** o una licencia del complemento **Audioconferencia**.
    
4. En la página **Agregar nuevos números de servicio**, use los menús desplegables para elegir lo siguiente:
    
  - **País o región**
    
  - **Estado o región**
    
  - **Ciudad**
    
5. En **Cantidad**, introduzca el número de números de teléfono que quiere para su organización y haga clic en **Agregar** para crear una reserva. Tiene 10 minutos para seleccionar sus números de teléfono y, si tarda más de estos 10 minutos, estos números de teléfono se devolverán al grupo de números de teléfono.
    
    > [!NOTE]
    > Puede ver la cantidad de números de teléfono que se basa en el número de licencias que aparecen junto a **Número de usuarios totales que puede adquirir**. 
  
6. Puede hacer clic en **Mostrar números** para ver la lista completa de números de teléfono. Esto resulta útil si no desea seleccionar un número de teléfono concreto de la lista.
    
7. Seleccione los números de teléfono que desee y haga clic en **Adquirir números**.
    
### Asignar números de servicio

Cuando tenga sus números de servicio, pueden asignarse a un puente de conferencias de acceso telefónico local. Para ello, consulte [Cambiar el pago o gratuito números de pago en el puente de conferencia de Audio](../audio-conferencing-in-office-365/change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
  
### Portabilidad o trasferencia de números de servicio existentes

Si quiere transferir números de servicio de su proveedor de servicios u operador de telefonía actual, debe enviar manualmente una solicitud de portabilidad a Microsoft. Tiene que presentar solicitudes de portabilidad separadas para cada tipo de número de servicio (gratuito o pago) que vaya a transferir mediante una Carta de autorización (LOA). En la Carta de autorización (LOA), debe seleccionar el tipo correcto de número de servicio. Al ponerse en contacto con el soporte técnico de Microsoft, asegúrese de especificar que está transfiriendo un número de servicio ( *y no un número de usuario o suscriptor*  ) o la capacidad de llamadas simultáneas tal vez no sea suficiente para hacer frente a los volúmenes de llamadas. Si quiere conocer más acerca de cómo enviar una solicitud de portabilidad, consulte[Enviar manualmente una solicitud de servicio personalizado](../what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request.md).
  
## Expandir para ver cuántos números de teléfono se pueden obtener

Al obtener números de teléfono para su organización, puede obtener más números de teléfono que los que le corresponden por las licencias que tiene asignadas. Sin embargo, esto depende de los tipos de números de teléfono y del tipo de licencias que ha adquirido y asignado.
  
Puede ver la cantidad de números de teléfono que puede obtener en la página **Números de teléfono** del Centro de administración de Skype Empresarial o bien puede ejecutar el cmdlet[Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/en-us/library/mt634605.aspx). 
  
> [!IMPORTANT]
> Los siguientes límites no incluyen números de teléfono en los que haya realizado portabilidad o que haya transferido a Microsoft. 
  
||||
|:-----|:-----|:-----|
|**Este es el tipo de número de teléfono** <br/> |**¿Cómo se obtiene el total de números de teléfono?** <br/> |**Este es un ejemplo** <br/> |
|Número de usuario (suscriptor)  <br/> |La cantidad de números de teléfono es igual a la cantidad total de licencias de planes de llamadas de voz  *nacionales + nacionales e internacionales*  , multiplicado por 1,1, y 10 números más que se proporcionan. <br/> |Si dispone de 50 usuarios en total con planes de llamadas de voz nacionales y nacionales e internacionales, puede adquirir **65** números de teléfono **(50 x 1,1 + 10)**. <br/> |
|Número de servicio de pago  <br/> | La cantidad de números de teléfono es igual a la cantidad total de licencias de *PBX en la nube + Conferencia RTC*  y utiliza lo siguiente: <br/>  Si hay **1-25 licencias**, se proporcionan **5** números de teléfono. <br/>  Si hay **26-49 licencias**, se proporcionan **10** números de teléfono. <br/>  Si hay **50-99 licencias**, se proporcionan **20** números de teléfono. <br/>  Si hay **100-149 licencias**, se proporcionan **30** números de teléfono. <br/>  Si hay **150-199 licencias**, se proporcionan **40** números de teléfono. <br/>  Si hay **200-499 licencias**, se proporcionan **65** números de teléfono. <br/>  Si hay **500-749 licencias**, se proporcionan **90** números de teléfono. <br/>  Si hay **750-999 licencias**, se proporcionan **110** números de teléfono. <br/>  Si hay **1.000-1.249 licencias**, se proporcionan **125** números de teléfono. <br/>  Si hay **1.250-1.499 licencias**, se proporcionan **135** números de teléfono. <br/>  Si hay **1.500-1.999 licencias**, se proporcionan **160** números de teléfono. <br/>  Si hay **2.000-2.999 licencias**, se proporcionan **210** números de teléfono. <br/>  Si hay **3.000-6.999 licencias**, se proporcionan **420** números de teléfono. <br/>  Si hay **7.000-9.999 licencias**, se proporcionan **500** números de teléfono. <br/>  Si hay **10.000-14.999 licencias**, se proporcionan **600** números de teléfono. <br/>  Si hay **15.000-19.999 licencias**, se proporcionan **700** números de teléfono. <br/>  Si hay **20.000-49.999 licencias**, se proporcionan **1000** números de teléfono. <br/>  Si hay **más de 50.000**, se proporcionan **1.500** números de teléfono. <br/> |Si tiene un total de **51** licencias de PBX en la nube y Conferencia RTC, puede obtener **20** números de servicio de pago. <br/> |
|Número de servicio gratuito  <br/> | La cantidad de números de teléfono es igual a la cantidad total de licencias de *PBX en la nube + Conferencia RTC*  y utiliza lo siguiente: <br/>  Si hay **1-25 licencias**, se proporcionan **5** números de teléfono. <br/>  Si hay **26-49 licencias**, se proporcionan **10** números de teléfono. <br/>  Si hay **50-99 licencias**, se proporcionan **20** números de teléfono. <br/>  Si hay **100-149 licencias**, se proporcionan **30** números de teléfono. <br/>  Si hay **150-199 licencias**, se proporcionan **40** números de teléfono. <br/>  Si hay **200-499 licencias**, se proporcionan **65** números de teléfono. <br/>  Si hay **500-749 licencias**, se proporcionan **90** números de teléfono. <br/>  Si hay **750-999 licencias**, se proporcionan **110** números de teléfono. <br/>  Si hay **1.000-1.249 licencias**, se proporcionan **125** números de teléfono. <br/>  Si hay **1.250-1.499 licencias**, se proporcionan **135** números de teléfono. <br/>  Si hay **1.500-1.999 licencias**, se proporcionan **160** números de teléfono. <br/>  Si hay **2.000-2.999 licencias**, se proporcionan **210** números de teléfono. <br/>  Si hay **3.000-6.999 licencias**, se proporcionan **420** números de teléfono. <br/>  Si hay **7.000-9.999 licencias**, se proporcionan **500** números de teléfono. <br/>  Si hay **10.000-14.999 licencias**, se proporcionan **600** números de teléfono. <br/>  Si hay **15.000-19.999 licencias**, se proporcionan **700** números de teléfono. <br/>  Si hay **20.000-49.999 licencias**, se proporcionan **1000** números de teléfono. <br/>  Si hay **más de 50.000**, se proporcionan **1.500** números de teléfono. <br/> |Si tiene un total de **1.001** licencias de PBX en la nube y Conferencia RTC, puede obtener **125** números de servicio gratuitos. <br/> > [!IMPORTANT]> Es necesario disponer de [Configurar comunicaciones créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) para reservar y utilizar números de teléfono gratuitos.          |
   
> [!NOTE]
> Si necesita obtener más números de teléfono, consulte [Póngase en contacto con el soporte de Office 365 para empresas: ayuda para administradores](http://technet.microsoft.com/library/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b%28Office.14%29.aspx). 
  
## Temas relacionados

[Términos y condiciones de las llamadas de emergencias](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)
  
[Período de llamada de salida complementario de conferencias de audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  

