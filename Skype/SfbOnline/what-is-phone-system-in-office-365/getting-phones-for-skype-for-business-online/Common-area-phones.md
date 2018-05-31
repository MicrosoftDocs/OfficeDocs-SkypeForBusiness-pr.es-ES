---
title: Configurar teléfonos de área común
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar las opciones de teléfonos de área común.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: 12ed7d5c24649903f7cd3020d66ee4e9fcb77b6f
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "19117513"
---
# <a name="set-up-common-area-phones"></a>Configurar teléfonos de área común

Un teléfono de área común o CAP, es normalmente se colocan en un área compartido y no asociado a un usuario individual. Por ejemplo, un teléfono de área de recepción de teléfono puerta teléfono o salas de reuniones, mayúsculas se configuran como dispositivos en lugar de los usuarios e inicie sesión automáticamente en la red. En los pasos siguientes, le ayudaremos a configurar una cuenta de sistema de teléfono de Microsoft con planes de llamar a y, a continuación, implementar un extremo.

## <a name="prerequisites-for-common-area-phones"></a>Requisitos previos para teléfonos de área común

Confirme que dispone de lo siguiente:

    - Adquirido SKU de teléfono de área común 
    - Firmware actualizado (vea admiten Firmware de temahttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
    - Teléfonos aprobados (ver la lista enhttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones) 

## <a name="check-the-firmware-for-your-phone"></a>Comprobar el firmware de su teléfono
- **Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.
- **Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.
- **Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**. 
- **Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.

Actualizaciones de firmware se administran mediante el Skype para servicio empresarial. Cada Skype para la empresa certificada firmware del teléfono se cargó en la Skype para servidor de actualización de negocio, y actualización de dispositivos está habilitado en todos los teléfonos de forma predeterminada. 

Según el tiempo de inactividad en el teléfono y los intervalos de sondeo, teléfonos automáticamente descargar e instalar las compilaciones certificadas más recientes. Puede deshabilitar la configuración de actualización de dispositivo mediante el cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) y establecer el parámetro _EnableDeviceUpdate_ en `false`.

## <a name="create-cap"></a>Crear CAP
Cree el extremo mediante la configuración de la configuración antes de configurar el teléfono físico.

#### <a name="purchase-the-common-area-phone-sku"></a>El teléfono de área común SKU de compra. 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a>Configurar el teléfono de área común<!-- this section could use a screen shot-->

**Crear usuario** 
1. Asignar el teléfono de área común SKU
2. Asignar una llamada a planear (si se usa el sistema telefónico de Microsoft con planes de llamada). 
3. Asignar a un número de teléfono disponibles en el Skype para el centro de administración de negocio, o solicitar un nuevo número de teléfono.

**Crear nuevo usuario**

1. En el panel de aprovisionamiento, tienen una opción para escribir un nombre y el apellido (por ejemplo, recepción principal).
2. Escriba un nombre para mostrar (requerido), por ejemplo, "Main recepción".
3. Escriba un nombre de usuario (obligatorio), por ejemplo "MainReception" @"dominio" (nombre de la compañía o enterprise)
4. Escriba la ubicación (país).

**Asignar el teléfono de área común SKU** En el centro de administración de Office 365, vaya a **facturación > Servicios de compra** y agregue el **Teléfono de área común**

**Asignar el Plan de llamadas en SKU de capital**

1. Seleccione un Plan de llamada para habilitar el teléfono. 
2. Agregar el capital para habilitar el sistema telefónico y Skype para Online Plan 2 de negocio en el SKU de capital. <!-- odd order for step -->

**Asignar a un número de teléfono**
1. Buscar números de teléfono disponibles en **voz > números de teléfono**.
2. Seleccione un número en la lista disponible del número de números de teléfono.
3. Confirme la selección mediante la selección de **voz** y **Los números de teléfono**.

    >[Nota] Los usuarios de voz mostrarán sólo si tiene la licencia del sistema telefónico aplicada, aunque incluso después de aplicar, puede tardar tiempo para actualizar. En algún momento volver a abrir Skype para administración empresarial centro de ayuda.
    
## <a name="configure-phone"></a>Configurar el teléfono

**Preparar los teléfonos físicos**

El teléfono elegido debe tener el modo de teléfono de área común. 

***Teléfono Polycom VVX de ejemplo***

Habilitar el modo de teléfono de área común para el VVX Polycom siguiendo estos pasos:
1. En el explorador, use la interfaz web para habilitar el modo de CAP en el VVX
2. Vaya a **configuración** y en la Skype para la opción de configuración de negocio, seleccione **Teléfono de área común**.
3. Haga clic en **Sí** para guardar las opciones de configuración.

Ahora que está habilitado el modo de teléfono de capital, configurar el teléfono mediante la pantalla del teléfono. La presentación debe mostrar "CaAP está habilitado."

1. Haga clic en **configuración**.
2. Seleccione **avanzada**.
3. Escriba la contraseña.
4. En la configuración de administración, seleccione **Configuración de teléfono de área común**.
5. Habilitar el **modo de administración de CAP**y **CAP** .
6. Haga clic en **Guardar configuración**.

El teléfono está listo para aprovisionarse, que hará al iniciar sesión en la pantalla principal.

1. Iniciar sesión mediante la selección de **configuración** > **características** > **Skype para la empresa.**
2. Seleccione **Las credenciales de usuario**y seleccione **Inicio de sesión de web (CAP)** para generar un código..
3. Vaya al portal de aprovisionamiento en http://aka.ms/skypecape iniciar sesión como **Administrador**.
4. Escriba el nombre para mostrar (por ejemplo, Main recepción) para ver su extremo.

>[Nota] Si "Búsqueda para teléfonos de área común sólo" está desprotegido, desactive la casilla de verificación y volver a buscar.

5. En la ventana de código de emparejamiento, escriba el código que aparece en el teléfono y haga clic en **aprovisionar**.

Después de este último paso, el teléfono debe iniciar sesión automáticamente.

Encontrará más información acerca de los teléfonos disponibles [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).


