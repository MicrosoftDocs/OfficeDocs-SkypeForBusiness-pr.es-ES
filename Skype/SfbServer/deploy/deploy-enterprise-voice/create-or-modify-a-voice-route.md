---
title: Crear o modificar una ruta de voz de Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Resumen: Obtenga información sobre cómo crear o modificar una ruta de voz de Skype para Business Server mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 3704e973e392337700effc0d4c3278656f706d73
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21013206"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Crear o modificar una ruta de voz de Skype para la empresa
 
**Resumen:** Obtenga información sobre cómo crear o modificar una ruta de voz de Skype para Business Server mediante el uso de la Skype para el Panel de Control de servidor empresarial.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Para crear una ruta de voz mediante el Skype para el Panel de Control de servidor empresarial

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Haga clic en **Ruta**.
    
5. Haga clic en **Nueva** para mostrar el cuadro de diálogo **Ruta de voz nueva**.
    
6. En el campo **Nombre**, escriba un nombre descriptivo para la ruta de voz.
    
7. (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.
    
8. Para especificar los patrones que desea que incluya esta ruta, puede usar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
   - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores como se indica a continuación. Puede especificar dos tipos de patrón de coincidencia:
    
   - **Dígitos iniciales para números que quiera permitir**: introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba +425 y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
    
   - **Excepciones**: si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba en uno o más valores para la coincidencia de patrones que desee *no* esto enrutar para dar cabida a hacer. Por ejemplo, para excluir los números con +425237 desde la ruta inicial, escriba un valor de + 425237 en el campo de **excepciones** y, a continuación, haga clic en **Aceptar**.
    
   - Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta. Para obtener información detallada sobre cómo escribir expresiones regulares, consulte ["expresiones regulares de .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Si no desea que el identificador de la que realiza la llamada saliente que aparezca para el destinatario de la llamada de teléfono, seleccione **identificador de autor de la llamada de suprimir** . Si selecciona esta opción, debe especificar un **identificador de autor de la llamada alternativas** que aparecerá en el autor de la llamada del destinatario para mostrar del identificador.
    
10. Para asociar uno o más troncos a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.
    
11. Para asociar uno o más registros de uso de la red de telefonía conmutada (RTC) con la ruta de voz, haga clic en **Seleccionar** y elija un registro en la lista de registros de uso de RTC que se hayan definido para la implementación de Telefonía IP empresarial.
    
    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, vea [los registros de uso de RTC de vista en Skype para la empresa](view-pstn-usage-records.md). > Para crear o editar registros de uso de RTC, consulte [crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa](voice-policy-and-pstn-usage-records.md)
  
12. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre de registro y haga clic en arriba o flecha abajo.
    
    > [!NOTE]
    > A diferencia de una directiva de voz, donde el orden en que se enumeran los registros de uso de RTC es importante, el orden en que RTC se muestran los registros de uso en la ruta de voz es insignificante. Sin embargo, se recomienda que organice la lista por frecuencia de uso. Por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype para Business Server recorre la lista desde la parte superior hacia abajo.) 
  
13. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
14. Haga clic en **Aceptar** para guardar la ruta de voz.
    
    > [!IMPORTANT]
    > Al crear una ruta de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>Para modificar una ruta de voz

1. Abra Skype para el Panel de Control de servidor empresarial.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Ruta**.
    
3. En la página **Ruta**, use uno de los métodos siguientes para modificar una ruta de voz:
    
   - Haga clic en el nombre de una ruta de voz, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
   - Haga clic en el nombre de una ruta de voz, haga clic en **Editar**, en **Copiar** y, a continuación, en **Pegar**. Haga clic en la copia nueva de la ruta de voz que acaba de crear, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
4. En el campo **Nombre** en la página **Editar ruta de voz**, escriba un nombre descriptivo para la ruta de voz.
    
5. (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.
    
6. Para especificar los patrones que desea que incluya esta ruta, puede utilizar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
   - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores como se indica a continuación. Puede especificar dos tipos de patrón de coincidencia:
    
   - **Dígitos iniciales para números que quiera permitir**: introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba +425 y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
    
   - **Excepciones**: si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba en uno o más valores para la coincidencia de patrones que desee *no* esto enrutar para dar cabida a hacer. Por ejemplo, para excluir los números con +425237 desde la ruta inicial, escriba un valor de + 425237 en el campo de **excepciones** y, a continuación, haga clic en **Aceptar**.
    
   - Para definir el patrón coincidente de forma manual, haga clic en **Editar** en la herramienta de **creación de un patrón para que coincida con** y, a continuación, escriba en una expresión regular de .NET Framework para especificar el patrón coincidente para los números de teléfono de destino a la que se aplica la ruta. Para obtener información detallada sobre cómo escribir expresiones regulares, consulte ["expresiones regulares de .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Seleccione **Suprimir identificador de autor de la llamada** si no desea que el identificador del teléfono que está realizando la llamada saliente que aparezca para el destinatario de la llamada. Si selecciona esta opción, debe especificar un **identificador de autor de la llamada alternativas** que aparecerá en el autor de la llamada del destinatario para mostrar del identificador.
    
8. Para asociar uno o más troncos de red telefónica conmutada (RTC) a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.
    
9. Para asociar uno o varios usos de RTC con la ruta de voz, haga clic en **Seleccionar** y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación de Enterprise Voice.
    
    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, vea [los registros de uso de RTC de vista en Skype para la empresa](view-pstn-usage-records.md). > Para crear o editar registros de uso de RTC, consulte [crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa](voice-policy-and-pstn-usage-records.md). 
  
10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre de registro y haga clic en arriba o flecha abajo.
    
    > [!NOTE]
    > Al contrario de lo que sucede con las directivas de voz donde el orden en el que aparecen los registros de uso de RTC es importante, en una ruta de voz, el orden carece de importancia. Sin embargo, recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype para Business Server recorre la lista desde la parte superior hacia abajo.) 
  
11. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
12. Haga clic en **Aceptar**.
    
13. En la página **Ruta**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Al crear o modificar una ruta de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.
  
## <a name="see-also"></a>Vea también

[Ver registros de uso de RTC de Skype para la empresa](view-pstn-usage-records.md)
  
[Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa](voice-policy-and-pstn-usage-records.md)
  
[Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md)

