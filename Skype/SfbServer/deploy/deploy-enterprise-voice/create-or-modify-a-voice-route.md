---
title: Crear o modificar una ruta de voz en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Resumen: Aprenda a crear o modificar una ruta de voz en Skype empresarial Server mediante el panel de control de Skype empresarial Server.'
ms.openlocfilehash: f79e672b45f68e09391489da55023dceb3b0dd93
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286214"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Crear o modificar una ruta de voz en Skype empresarial
 
**Resumen:** Para obtener más información sobre cómo crear o modificar una ruta de voz en Skype empresarial Server, use el panel de control de Skype empresarial Server.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Para crear una ruta de voz con el panel de control de Skype empresarial Server

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Haga clic en **Ruta**.
    
5. Haga clic en **Nueva** para mostrar el cuadro de diálogo **Ruta de voz nueva**.
    
6. En el campo **Nombre**, escriba un nombre descriptivo para la ruta de voz.
    
7. (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.
    
8. Para especificar los patrones que desea que incluya esta ruta, puede usar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
   - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores como se indica a continuación. Puede especificar dos tipos de patrón de coincidencia:
    
   - **Dígitos iniciales para números que quiera permitir**: introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba + 425 y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
    
   - **Excepciones**: si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba uno o más valores para los patrones de coincidencia que *no* desea que se adapten a este enrutamiento. Por ejemplo, para excluir números que empiecen por + 425237 de la ruta, escriba un valor de + 425237 en el campo **excepciones** y, a continuación, haga clic en **Aceptar**.
    
   - Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta. Para obtener más información sobre cómo escribir expresiones regulares, vea ["expresiones regulares de .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Seleccione **suprimir la identificación de llamadas** si no desea que el identificador del teléfono que hace la llamada saliente aparezca al destinatario de la llamada. Si selecciona esta opción, debe especificar un identificador de **llamada alternativo** que aparecerá en la pantalla de identificación de llamadas del destinatario.
    
10. Para asociar uno o más troncos a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.
    
11. Para asociar uno o más registros de uso de la red de telefonía conmutada (RTC) con la ruta de voz, haga clic en **Seleccionar** y elija un registro en la lista de registros de uso de RTC que se hayan definido para la implementación de Telefonía IP empresarial.
    
    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, consulte [ver los registros de uso de RTC en Skype empresarial](view-pstn-usage-records.md). > crear o editar registros de uso de RTC, consulte [crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype empresarial](voice-policy-and-pstn-usage-records.md)
  
12. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    
    > [!NOTE]
    > En contraste con una directiva de voz, donde el orden en el que se muestran los registros de uso de RTC es importante, el orden en que aparecen los registros de uso de RTC en la ruta de voz es inimportante. Sin embargo, le recomendamos que organice la lista según la frecuencia de uso. Por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype empresarial Server recorre la lista desde arriba hacia abajo). 
  
13. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
14. Haga clic en **Aceptar** para guardar la ruta de voz.
    
    > [!IMPORTANT]
    > Al crear una ruta de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración del enrutamiento de voz en Skype empresarial](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>Para modificar una ruta de voz

1. Abra el panel de control de Skype empresarial Server.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Ruta**.
    
3. En la página **Ruta**, use uno de los métodos siguientes para modificar una ruta de voz:
    
   - Haga clic en el nombre de una ruta de voz, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
   - Haga clic en el nombre de una ruta de voz, haga clic en **Editar**, en **Copiar** y, a continuación, en **Pegar**. Haga clic en la copia nueva de la ruta de voz que acaba de crear, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
4. En el campo **Nombre** en la página **Editar ruta de voz**, escriba un nombre descriptivo para la ruta de voz.
    
5. (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.
    
6. Para especificar los patrones que desea que incluya esta ruta, puede utilizar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
   - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores como se indica a continuación. Puede especificar dos tipos de patrón de coincidencia:
    
   - **Dígitos iniciales para números que quiera permitir**: introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba +425 y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
    
   - **Excepciones**: si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba uno o más valores para los patrones de coincidencia que *no* desea que se adapten a este enrutamiento. Por ejemplo, para excluir números que empiecen por + 425237 de la ruta, escriba un valor de + 425237 en el campo **excepciones** y, a continuación, haga clic en **Aceptar**.
    
   - Para definir el patrón de coincidencia de forma manual, haga clic en **Editar** en la herramienta **crear un patrón para coincidir** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente para los números de teléfono de destino a los que se aplica la ruta. Para obtener más información sobre cómo escribir expresiones regulares, vea ["expresiones regulares de .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Seleccione **suprimir la identificación de llamadas** si no desea que el identificador del teléfono que hace la llamada saliente aparezca al destinatario de la llamada. Si selecciona esta opción, debe especificar un identificador de **llamada alternativo** que aparecerá en la pantalla de identificación de llamadas del destinatario.
    
8. Para asociar uno o más troncos de red telefónica conmutada (RTC) a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.
    
9. Para asociar uno o más usos de RTC con la ruta de voz, haga clic en **seleccionar** y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación de telefonía IP empresarial.
    
    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, consulte [ver los registros de uso de RTC en Skype empresarial](view-pstn-usage-records.md). > crear o editar registros de uso de RTC, consulte [crear o modificar una directiva de voz y configurar los registros de uso de RTC en Skype empresarial](voice-policy-and-pstn-usage-records.md). 
  
10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    
    > [!NOTE]
    > Al contrario de lo que sucede con las directivas de voz donde el orden en el que aparecen los registros de uso de RTC es importante, en una ruta de voz, el orden carece de importancia. Sin embargo, recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype empresarial Server recorre la lista desde arriba hacia abajo). 
  
11. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
12. Haga clic en **Aceptar**.
    
13. En la página **Ruta**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Al crear o modificar una ruta de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.
  
## <a name="see-also"></a>Vea también

[Ver los registros de uso de RTC en Skype empresarial](view-pstn-usage-records.md)
  
[Crear o modificar una directiva de voz y configurar los registros de uso de RTC en Skype empresarial](voice-policy-and-pstn-usage-records.md)
  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Skype empresarial](voice-route-config-changes.md)

