---
title: Crear o modificar una ruta de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Resumen: Conozca cómo crear o modificar una ruta de voz de Skype para Business Server 2015 mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 2adc4d2a1277f229c1fcfbf230a49d5e91855a97
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business-2015"></a>Crear o modificar una ruta de voz en Skype Empresarial 2015
 
**Resumen:** Aprenda a crear o modificar una ruta de voz de Skype para Business Server 2015 utilizando el Skype para el Panel de Control de servidor empresarial.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Para crear una ruta de voz mediante el Skype para el Panel de Control de servidor empresarial

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Haga clic en **Ruta**.
    
5. Haga clic en **Nueva** para mostrar el cuadro de diálogo **Ruta de voz nueva**.
    
6. En el campo **Nombre**, escriba un nombre descriptivo para la ruta de voz.
    
7. (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.
    
8. Para especificar los patrones que desea que incluya esta ruta, puede usar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
   - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores como se indica a continuación. Puede especificar dos tipos de patrón de coincidencia:
    
   - **Dígitos iniciales para números que quiera permitir**: introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba +425 y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
    
   - **Excepciones**: si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba en uno o más valores para la coincidencia de patrones que usted realice desee *no* esta ruta para acomodar. Por ejemplo, para excluir números a partir de +425237 de la ruta, introduzca un valor de + 425237 en el campo de **las excepciones** y, a continuación, haga clic en **Aceptar**.
    
   - Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta. Para obtener más información sobre cómo escribir expresiones regulares, vea ["expresiones regulares de.NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Si no desea que el identificador del que realiza la llamada saliente que parezca que el destinatario de la llamada de teléfono, seleccione **identificador de suprimir** . Si selecciona esta opción, debe especificar un **identificador alternativo** que aparecerá en el llamador del destinatario mostrar ID.
    
10. Para asociar uno o más troncos a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.
    
11. Para asociar uno o más registros de uso de la red de telefonía conmutada (RTC) con la ruta de voz, haga clic en **Seleccionar** y elija un registro en la lista de registros de uso de RTC que se hayan definido para la implementación de Telefonía IP empresarial.
    
    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso disponibles PSTN, consulte [registros de uso de vista PSTN en Skype para negocios 2015](view-pstn-usage-records.md). > Para crear o editar registros de uso PSTN, consulte [crear o modificar una directiva de voz y configurar registros de uso PSTN en Skype para negocios 2015](voice-policy-and-pstn-usage-records.md)
  
12. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en arriba o flecha abajo.
    
    > [!NOTE]
    > A diferencia de una directiva de voz, donde el orden en que se enumeran los registros de uso PSTN es importante, el orden en que PSTN registros de uso se enumeran en la ruta de voz es insignificante. Sin embargo, recomendamos que organice la lista por frecuencia de uso. Por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype para Business Server recorre la lista desde arriba hacia abajo.) 
  
13. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
14. Haga clic en **Aceptar** para guardar la ruta de voz.
    
    > [!IMPORTANT]
    > Al crear una ruta de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>Para modificar una ruta de voz

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Ruta**.
    
3. En la página **Ruta**, use uno de los métodos siguientes para modificar una ruta de voz:
    
   - Haga clic en el nombre de una ruta de voz, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
   - Haga clic en el nombre de una ruta de voz, haga clic en **Editar**, en **Copiar** y, a continuación, en **Pegar**. Haga clic en la copia nueva de la ruta de voz que acaba de crear, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
4. En el campo **Nombre** en la página **Editar ruta de voz**, escriba un nombre descriptivo para la ruta de voz.
    
5. (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.
    
6. Para especificar los patrones que desea que incluya esta ruta, puede utilizar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
   - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores como se indica a continuación. Puede especificar dos tipos de patrón de coincidencia:
    
   - **Dígitos iniciales para números que quiera permitir**: introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba +425 y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
    
   - **Excepciones**: si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba en uno o más valores para la coincidencia de patrones que usted realice desee *no* esta ruta para acomodar. Por ejemplo, para excluir números a partir de +425237 de la ruta, introduzca un valor de + 425237 en el campo de **las excepciones** y, a continuación, haga clic en **Aceptar**.
    
   - Para definir manualmente el modelo coincidente, haga clic en **Editar** en la herramienta de **generación de un modelo de coincidencia** y, a continuación, escriba en una expresión regular de.NET Framework para especificar el modelo coincidente para números de teléfono de destino al que se aplica la ruta. Para obtener más información sobre cómo escribir expresiones regulares, vea ["expresiones regulares de.NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Seleccione **Suprimir caller ID** si no desea que el ID del teléfono que está realizando la llamada saliente que aparezca en el destinatario de la llamada. Si selecciona esta opción, debe especificar un **identificador alternativo** que aparecerá en el llamador del destinatario mostrar ID.
    
8. Para asociar uno o más troncos de red telefónica conmutada (RTC) a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.
    
9. Para asociar uno o varios usos de RTC con la ruta de voz, haga clic en **Seleccionar** y elija un registro en la lista de registros de uso de RTC que se han definido para la implementación de Telefonía IP empresarial.
    
    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso disponibles PSTN, consulte [registros de uso de vista PSTN en Skype para negocios 2015](view-pstn-usage-records.md). > Para crear o editar registros de uso PSTN, consulte [crear o modificar una directiva de voz y configurar registros de uso PSTN en Skype para el año 2015 Business](voice-policy-and-pstn-usage-records.md). 
  
10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en arriba o flecha abajo.
    
    > [!NOTE]
    > Al contrario de lo que sucede con las directivas de voz donde el orden en el que aparecen los registros de uso de RTC es importante, en una ruta de voz, el orden carece de importancia. Sin embargo, recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype para Business Server recorre la lista desde arriba hacia abajo.) 
  
11. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
12. Haga clic en **Aceptar**.
    
13. En la página **Ruta**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Al crear o modificar una ruta de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.
  
## <a name="see-also"></a>Vea también

#### 

[Ver los registros de uso PSTN en Skype para negocios 2015](view-pstn-usage-records.md)
  
[Crear o modificar una directiva de voz y configurar registros de uso PSTN en Skype para negocios 2015](voice-policy-and-pstn-usage-records.md)
  
[Publicar los cambios pendientes a la configuración de enrutamiento de voz de Skype para negocios 2015](voice-route-config-changes.md)

