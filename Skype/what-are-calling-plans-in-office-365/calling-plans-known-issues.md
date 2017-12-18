---
title: "Llamar a los problemas conocidos de planes"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0

description: "Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. "
---

# Llamar a los problemas conocidos de planes

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Planes de llamada en Office 365 son una nueva característica que se encuentra en Skype Empresarial Online. Los siguientes son problemas actuales que se controlan y conocidas investigar. Se le resuelto potencialmente cuando se actualiza la característica en futuras versiones de Office 365 y Skype Empresarial Online.
  
## Llamar a los problemas conocidos de planes

|**Problema conocido**|**Comentarios**|
|:-----|:-----|
|Realizar la transición de Technical Preview licencias a licencias de producción para llamar a los planes no actualizan automáticamente la licencia.  <br/> |Comprar sus nuevas licencias en primer lugar, por lo que está listos para asignar a los usuarios. Quitar la licencia de promoción (Technical Preview) a un usuario y asignar después **inmediatamente** el nuevo **Llamar a planear nacionales** o **Llamar a planear internacional** licencias al usuario. <br/> Si va a quitar y agregar licencias para varios usuarios, es muy importante que quitar las licencias de todos los usuarios con Windows PowerShell y, a continuación, asignar **inmediatamente** las licencias para todos los usuarios también con Windows PowerShell. Esto se asegurará de que no hay ninguna interrupción en el servicio al tratar grandes volúmenes de asignaciones de licencia de usuario. Para los scripts de PowerShell de ejemplo, vea[Asignar Skype para Business y Microsoft Teams licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> > [!NOTE]> Si está utilizando la conectividad de RTC local para usuarios de híbrido,  *solo*  tendrán que asigne una licencia de **Sistema telefónico**. **No** debe asignar también una planear una llamada de voz.> Sin embargo, si va a habilitar llamar a los planes de Office 365 para los usuarios que están en Office 365, debe seguir asignar una licencia de **Llamar a planear nacionales** o **Llamar a planear internacional** para esos usuarios. Vea[Asignar Skype para Business y Microsoft Teams licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).           |
   
## Temas relacionados

[Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)
  
[Período de llamada de salida complementario de conferencias de audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

