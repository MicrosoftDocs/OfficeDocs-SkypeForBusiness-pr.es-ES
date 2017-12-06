---
title: "¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.AddressAndLocation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
description: "Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. "
---

# ¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](589bf5f5-490a-4215-8588-99bab7d33e31.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/589bf5f5-490a-4215-8588-99bab7d33e31). 
  
Al configurar llamar a los planes de Office 365, se requiere que una dirección de emergencia asignarse a cada número de teléfono cuando se obtiene el número de teléfono o su asignada a un usuario para admitir llamadas de emergencia. Antes de asignar una dirección de emergencia a un número de teléfono, debe crear una dirección de emergencia y valida. La validación garantiza que la dirección de emergencia se reconoce y que está en un formato correcto que se pueden usar los servicios de emergencia respuesta. Si lo desea, una ubicación dentro de la dirección de emergencia se puede agregar a proporcionar una ubicación más específica para el usuario. Por ejemplo, la ubicación de emergencia podría ser un piso, ala u office que está vinculado a una dirección de emergencia específica. Aunque la dirección de emergencia se valida, no ubicaciones.
  
## ¿Qué son las direcciones de emergencia?

Una dirección de emergencia se requiere para los números de teléfono activa, pero cuando se requiere depende del país o región. En los Estados Unidos, es **necesaria** una dirección de emergencia cuando se asigna un número a un usuario. Para otros países, como en Europa, Oriente medio y África (EMEA), emergencia es **necesaria** una dirección cuando recibe el número de teléfono de Office 365, o cuando se transfiere desde otro proveedor de servicios o carrier.
  
Una dirección de emergencia puede hacer referencia a como una dirección, dirección postal o una dirección física. Es la dirección postal o cívica de un lugar de la empresa para su organización. Por ejemplo, la dirección  *que 12345 Norte principales calle, Redmond, Washington 98052*  se utiliza para redirigir las llamadas de emergencia a las autoridades distribución apropiado y ayudar a localizar el llamador emergencia. Es probable que necesite más de una dirección de emergencia si su empresa tiene más de una ubicación de la empresa física.
  
Validar una dirección de emergencia implica asegurarse de que es legítimos y con el formato correcto para los servicios de emergencia respuesta. Es posible crear y guardar una dirección de emergencia que no se valida, pero solo validadas direcciones se pueden asociar a un usuario. Cuando una dirección de emergencia se valida y guarda, se puede asignar a un usuario. Si necesita cambiar una dirección de emergencia validada guardada, debe crear una nueva.
  
## ¿Qué son las ubicaciones de emergencia?

Ubicaciones de emergencias están asociadas a una dirección de emergencia para dar a una ubicación exacta más dentro de un edificio. Una ubicación de emergencia suele ser un piso, ala de creación o número de la oficina donde se encuentra el usuario. Puede tener un número ilimitado de ubicaciones asociadas a una dirección de emergencia.
  
Al asignar una dirección de emergencia a un usuario, se hace referencia a un Id. de ubicación al asignar la dirección. El Id. de ubicación incluye la dirección de emergencia (la calle o la dirección civil). Se incluye una ubicación de emergencia predeterminada con una dirección de emergencia cuando no son necesarias las ubicaciones dentro del edificio. 
  
## ¿Qué es un enrutamiento de llamadas SOS?

Ubicaciones y las direcciones de emergencias se usan durante el proceso de enrutamiento llamadas de emergencia al centro de distribución apropiado al distribuir emergencias equipos de primeros respuesta. Cuando un Skype para usuarios de empresa llama un número de emergencia, cómo la llamada se enruta el servicio público seguridad responder a punto (PSAP) varían según el país o región. En algunos países, como los Estados Unidos y Reino Unido, las llamadas se revisarán en primer lugar para determinar la ubicación actual del usuario antes de conectarse a la llamada al centro de distribución apropiado. En otros países o regiones, llamadas se le dirige directamente al centro de envío servir el número de teléfono asociado con el llamador emergencia.
  
## Crear, agregar y asignar ubicaciones de emergencias y direcciones a los usuarios

1. **Plan para ubicaciones de emergencias** El primer paso es planear las ubicaciones de emergencias. Necesario mostrar todas las direcciones físicas. A continuación, en función de ello, determinar si ubicaciones para las direcciones de emergencias son necesarias y si es así, ¿qué son. Por ejemplo, si una empresa tiene 3 edificios cada con 4 plantas, es probable que es necesario que haya 3 direcciones de emergencias con plantas 1-4, aparece como una ubicación para cada uno.
    
2. **Crear y validar las ubicaciones de emergencia**: el paso siguiente es crear y validar las direcciones de emergencia. Al crear una dirección de emergencia, puede validarla. Para crear una dirección de emergencia, vea [Agregar o quitar una dirección de emergencia para su organización](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > Validar una dirección postal o cívica implica asegurarse de que es legítimos y con formato correcto. Es posible que una dirección de emergencia parcialmente correcta, como un nombre de la ciudad escrito incorrectamente puede pasar todavía paso de validación. El proceso de validación utiliza todas las partes de una determinada dirección para determinar si contiene suficiente información para enrutar la llamada al centro de distribución de emergencia apropiado. Si es así, se devolverá como validada y, a continuación, se pueden asignar a un número de teléfono. 
  
3. **Obtener números de teléfono** El siguiente paso es obtener números de teléfono para los usuarios. Para ello, obteniendo nuevos números de teléfono de Office 365 o "trasladar" o transferir los números de teléfono existente sobre Office 365. Para ver los pasos completos, consulte[Números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Asignar números de teléfono** El último paso es permitir a los usuarios realizar y recibir llamadas telefónicas. Para ello, debe asignar a un número de teléfono para cada usuario. Vea[Asignar, cambiar o quitar un número de teléfono a un usuario](assign-change-or-remove-a-phone-number-for-a-user.md) para asignar a un número de teléfono.
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Skype empresarial Online: etiqueta de declinación de responsabilidades de emergencia llamar](https://go.microsoft.com/fwlink/?LinkID=692099)
  
[Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)
  
[Período de llamada de salida complementario de conferencias de audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

