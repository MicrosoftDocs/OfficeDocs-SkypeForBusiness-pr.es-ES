---
title: Aprovisionamiento remoto e inicio de sesión para dispositivos Teams Android
author: cazawideh
ms.author: czawideh
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Aprende a aprovisionar de forma remota e iniciar sesión en dispositivos Teams Android
ms.openlocfilehash: 4b3831bc42da92939c7aa61ff52a15266dc4a940
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674342"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Aprovisionamiento remoto e inicio de sesión para dispositivos Teams Android

Los administradores de TI pueden aprovisionar e iniciar sesión de forma remota en un dispositivo Teams Android. Para aprovisionar un dispositivo de forma remota, el administrador debe cargar los identificadores MAC de los dispositivos aprovisionados y crear un código de verificación. Todo el proceso se puede completar de forma remota desde el centro de administración de Teams.

## <a name="review-the-supported-devices"></a>Revisar los dispositivos compatibles

La siguiente lista muestra los requisitos Android firmware del dispositivo.

|Categoría de dispositivo|Modelo de dispositivo|Versión de firmware|
|---|---|---|
|teléfonos Teams|Yealink T55/T56/T58|58.15.0.124|
|teléfonos Teams|Yealink VP59|91.15.0.58|
|teléfonos Teams|Yealink CP960|73.15.0.117|
|teléfonos Teams|Yealink MP56/MP54/MP58|122.15.0.36|
|teléfonos Teams|Crestron UC-2|1.0.3.52|
|teléfonos Teams|Poly Trio C60|7.0.2.1071|
|teléfonos Teams|CCX400/CCX500/CCX600 |7.0.2.1072|
|teléfonos Teams|Códigos de audio C448HD/C450HD/C470HD|1.10.120|
|paneles Teams|Crestron 770/1070|1.004.0115|
|Salas de Teams en Android|Logitech Rally Bar Mini|1.2.982|
|Salas de Teams en Android|Logitech Rally Bar|1.2.982|
|Salas de Teams en Android|AudioCodes RXV80|1.13.361|
|Salas de Teams en Android|EPOS EXPAND Vision 3T|1.2.2.21182.10|
|Salas de Teams en Android|Yealink MeetingBar A30|133.15.0.60|
|Salas de Teams en Android|Yealink MeetingBar A20|133.15.0.60|
|Salas de Teams en Android|Consola táctil CTP18 de Yealink|137.15.0.37|
|Salas de Teams en Android|Poly Studio X30|3.5.0.344025|
|Salas de Teams en Android|Poly Studio X50|3.5.0.344025|
|Salas de Teams en Android|Consola táctil Poly TC8 |3.5.0.210489|
|Salas de Teams en Android|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>Agregar una dirección MAC del dispositivo

Completa los siguientes pasos para aprovisionar un nuevo dispositivo.

1. Inicie la sesión en el Centro de administración de Teams
2. Expande **Dispositivos Teams**.
3. Selecciona **Aprovisionar nuevo dispositivo** en la pestaña **Acciones** .

En la ventana **Aprovisionar nuevos dispositivos** , puede agregar la dirección MAC manualmente o cargar un archivo.

### <a name="manually-add-a-device-mac-address"></a>Agregar manualmente una dirección MAC del dispositivo

1. En la pestaña **Esperando activación** , seleccione **Agregar id**. de MAC.

   ![agregar manualmente una dirección mac del dispositivo.](../media/remote-provision-6-new.png)

1. Escriba el id. de MAC.
1. Escribe una ubicación que ayude a los técnicos a identificar dónde instalar los dispositivos.
1. Cuando termine, seleccione **Aplicar** .

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Upload un archivo para agregar una dirección MAC del dispositivo

1. En la pestaña **Esperando activación**, seleccione **Upload identificadores MAC**.
2. Descargue la plantilla de archivo.
3. Escriba el id. y la ubicación de MAC y, a continuación, guarde el archivo.
4. **Seleccione archivo** y, a continuación, seleccione **Upload**.

## <a name="generate-a-verification-code"></a>Generar un código de verificación

Necesitas un código de verificación para los dispositivos. El código de verificación se genera a granel o a nivel de dispositivo y es válido durante 24 horas.

1. En la pestaña **Esperando activación** , seleccione un id. de MAC existente.
   Se crea una contraseña para la dirección MAC y se muestra en la columna **Código de verificación** .

2. Proporcione la lista de id. de MAC y códigos de verificación a los técnicos de campo. Puede exportar los detalles directamente en un archivo y compartirlo con el técnico que realice el trabajo de instalación real.

## <a name="provision-the-device"></a>Aprovisionar el dispositivo

Cuando el dispositivo está encendido y conectado a la red, el técnico aprovisiona el dispositivo. Estos pasos se completan en el dispositivo Teams.

1. El técnico selecciona **Aprovisionar dispositivo** en la **Configuración**.  

   ![Aprovisionamiento de una nueva opción de dispositivo desde la pestaña Acciones.](../media/provision-device1.png)
  
2. El técnico introduce el código de verificación específico del dispositivo en el campo de entrada proporcionado.

   ![Aprovisionar la nueva verificación de dispositivo.](../media/provision-device-verification1.png)

   Una vez que el dispositivo se haya aprovisionado correctamente, el nombre del inquilino aparecerá en la página de inicio de sesión.

   ![Nombre del inquilino en la página de inicio de sesión.](../media/provision-code.png)

## <a name="first-time-remote-sign-in"></a>Inicio de sesión remoto por primera vez

El dispositivo aprovisionado aparece en la pestaña **Esperando inicio de sesión** . Inicia el proceso de inicio de sesión remoto seleccionando el dispositivo individual.

1. Selecciona un dispositivo en la pestaña **Esperando inicio de sesión** .

   ![La ventana con una lista de dispositivos listos para iniciar sesión.](../media/remote-device1.png)

2. Sigue las instrucciones de **Iniciar sesión como usuario** y, a continuación, selecciona **Cerrar**.

   ![la ventana Iniciar sesión en un usuario para un dispositivo individual.](../media/sign-in-user.png)

## <a name="related-articles"></a>Artículos relacionados

- [Administrar los dispositivos en Teams](device-management.md)
- [Inicio y cierre de sesión remotos](remote-sign-in-and-sign-out.md)
- [Actualizar Teams dispositivos de forma remota](remote-update.md)
