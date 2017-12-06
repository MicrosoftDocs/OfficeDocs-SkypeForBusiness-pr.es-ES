---
title: "Cómo se puede usar la identificación de llamadas en su organización"
ms.author: tonysmit
author: tonysmit
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
description: "Identificador de llamada se puede controlar para las llamadas entrantes y salientes para usuarios de sistema telefónico usando una directiva denominada CallingLineIdentity."
---

# Cómo se puede usar la identificación de llamadas en su organización

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](5a0bd8ba-3334-46ee-becf-1025597737f6.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/5a0bd8ba-3334-46ee-becf-1025597737f6). 
  
Identificador de llamada se puede controlar para las llamadas entrantes y salientes para usuarios de sistema telefónico usando una directiva denominada CallingLineIdentity.
  
La funcionalidad de identificador de llamada está disponible para todos los usuarios del sistema telefónico independientemente de la conectividad de RTC:
  
- Conectividad con RTC en línea
    
- Conectividad con RTC local con Skype Empresarial Cloud Connector Edition (requiere Cloud Connector Edition 1.4.2 y posterior)
    
- Conectividad con RTC local con Skype Empresarial Server (requiere Skype Empresarial Server 2015 CU5 y posterior)
    
> [!NOTE]
> Esta directiva no está disponible en Skype Empresarial 2015 Server. 
  
## Identificación de llamadas de salida

Hay tres opciones disponibles para la identificación de llamadas RTC de salida:
  
- El número de teléfono asignado al usuario, que es el valor predeterminado.
    
- Inventario de número de un número de teléfono que se clasifica como un  *servicio*  y número de *teléfono gratuito*  en su planes de llamada de teléfono de Office 365. Normalmente se asigna a una cola de llamada o de operador automático organizativa.
    
- Configurado como anónimo.
    
Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:
  
- Número de los números de teléfono que se clasifican como un  *usuario*  en su teléfono para llamar a los planes de inventario
    
- Un número de teléfono de Skype Empresarial Server local.
    
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md).
  
### Control de usuario final para la identificación de llamadas de salida

El atributo EnableUserOverride permite a los usuarios de uno o varios cambiar la configuración de su identificador de llamada a **anónimo**. Esto solo se aplica cuando una directiva CallingLineIdentity está configurada con un parámetro de CallingIDSubstitute de LineURI o sustituir. El valor predeterminado de EnableUserOverride es False.
  
Los usuarios finales puede establecer su identificador de llamada a **anónimo** mediante la pestaña **Llamar configuración hacia delante** en la Skype para cliente de escritorio de la empresa.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versión** <br/> |**Compatible** <br/> |
|Hacer clic y ejecutar  <br/> |Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Aplazar canal publicada de 13 de junio de 2017: versión 1701 (compilación 7766.2092)  <br/> |Sí  <br/> |
|MSI  <br/> |Skype Empresarial  <br/> |No  <br/> |
|Mac  <br/> |Skype Empresarial  <br/> |No  <br/> |
   
Sus usuarios finales también pueden configurar la identificación de llamadas en la página de configuración de usuario en: [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
  
## Identificación de llamadas de entrada

El atributo BlockIncomingCallerID permite para bloquear el identificador de llamada en llamadas entrantes de RTC. Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario. Y actualmente solo está disponible con conectividad de RTC en línea.
  
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)
  
[Período de llamada de salida complementario de conferencias de audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
[Skype para Business y Microsoft Teams licencias de complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

