---
title: Aprovisionamiento remoto e inicio de sesión para Teams dispositivos Android
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
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
description: Obtenga información sobre cómo aprovisionar e iniciar sesión de forma remota Teams dispositivos Android
ms.openlocfilehash: 668e50eab20d96f28ff7a6be49a0ddcac872b393
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733319"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Aprovisionamiento remoto e inicio de sesión para Teams dispositivos Android

Los administradores de TI pueden aprovisionar e iniciar sesión de forma remota en Teams dispositivo Android. Para aprovisionar un dispositivo de forma remota, el administrador debe cargar los IDs mac de los dispositivos que se aprovisionan y crear un código de verificación. Todo el proceso se puede completar de forma remota desde el Teams de administración.

## <a name="review-the-supported-devices"></a>Revisar los dispositivos compatibles

En la lista siguiente se muestran los requisitos de firmware del dispositivo Android.

|Categoría de dispositivo|Modelo de dispositivo|Versión de firmware|
|-|-|-|
|Teams teléfonos|Yealink T55/T56/T58|58.15.0.124|
|Teams teléfonos|Yealink VP59|91.15.0.58|
|Teams teléfonos|Yealink CP960|73.15.0.117|
|Teams teléfonos|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams teléfonos|Crestron UC-2|1.0.3.52|
|Teams teléfonos|  Poly Trio C60|  7.0.2.1071|
|Teams teléfonos|  CCX400/CCX500/CCX600    |7.0.2.1072|
|Teams teléfonos|  Códigos de audio C448HD/C450HD/C470HD|   1.10.120|
|Teams paneles|  Crestron 770/1070|  1.004.0115|
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

Complete los pasos siguientes para aprovisionar un nuevo dispositivo.

1. Inicie la sesión en el Centro de administración de Teams
2. Expandir **dispositivos**.
3. Seleccione **Aprovisionar nuevo dispositivo** en la **pestaña** Acciones.

En la **ventana Aprovisionar nuevos dispositivos,** puede agregar la dirección MAC manualmente o cargar un archivo.

### <a name="manually-add-a-device-mac-address"></a>Agregar manualmente una dirección MAC del dispositivo

1. En la **pestaña Activación en** espera, seleccione Agregar **id. de MAC.**

   ![agregar manualmente una dirección mac del dispositivo.](../media/remote-provision-6.png)

1. Escriba el id. de MAC.
1. Escriba una ubicación que ayude a los técnicos a identificar dónde instalar los dispositivos.
1. Seleccione **Aplicar** cuando haya terminado.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Upload un archivo para agregar una dirección MAC del dispositivo

1. En la **pestaña Activación en** espera, seleccione Upload de **MAC.**
2. Descargue la plantilla de archivo.
3. Escriba el id. y la ubicación de MAC y, después, guarde el archivo.
4. **Seleccione archivo** y, a continuación, **seleccione Upload**.

## <a name="generate-a-verification-code"></a>Generar un código de verificación

Necesita un código de verificación para los dispositivos. El código de verificación se genera en masa o en el nivel del dispositivo y es válido durante 24 horas.

1. En la **pestaña Activación en** espera, seleccione un id. de MAC existente.
   Se crea una contraseña para la dirección MAC y se muestra en la **columna Código de** verificación.

2. Proporcione la lista de los IDs MAC y los códigos de verificación a los técnicos de campo. Puede exportar los detalles directamente en un archivo y compartir el archivo con el técnico que está realizando el trabajo de instalación real.

## <a name="provision-the-device"></a>Aprovisionar el dispositivo

Cuando el dispositivo está encendido y conectado a la red, el técnico aprovisiona el dispositivo. Estos pasos se completan en Teams dispositivo.

1. El técnico selecciona **Aprovisionar dispositivo** en **el Configuración**.  

   ![Aprovisionar nueva opción de dispositivo desde la pestaña Acciones.](../media/provision-device1.png)
  
2. El técnico escribe el código de verificación específico del dispositivo en el campo de entrada proporcionado.

   ![Aprovisionar la verificación del nuevo dispositivo.](../media/provision-device-verification1.png)

   Una vez que el dispositivo se aprovisiona correctamente, el nombre del inquilino aparece en la página de inicio de sesión.

   ![Nombre del inquilino en la página de inicio de sesión.](../media/provision-code.png)

## <a name="sign-in-remotely"></a>Iniciar sesión de forma remota

El dispositivo aprovisionado aparece en la **pestaña Esperando inicio de sesión.** Inicie el proceso de inicio de sesión remoto seleccionando el dispositivo individual.

1. Seleccione un dispositivo en la **pestaña Esperando inicio de sesión.**

   ![La ventana con una lista de dispositivos listos para iniciar sesión.](../media/remote-device1.png)

2. Siga las instrucciones de **Iniciar sesión en un usuario** y, a continuación, seleccione **Cerrar**.

   ![la ventana Iniciar sesión en un usuario para un dispositivo individual.](../media/sign-in-user.png)

## <a name="related-article"></a>Artículo relacionado

- [Administrar los dispositivos en Teams](device-management.md)
- [Actualizar Teams dispositivos de forma remota](remote-update.md)
