---
title: Configurar Skype para llamar de Business Analytics
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: Configurar y utilizar Analytics llame a identificar y solucionar los problemas de calidad empresarial y Teams de Microsoft llamada de Skype.
ms.openlocfilehash: 287b45cf8363c03bf6b62cd68f8e2be681996101
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-skype-for-business-call-analytics"></a>Configurar Skype para llamar de Business Analytics

Como un Skype para la administración de negocios en línea, puede utilizar Analytics llamar a solucionar problemas de Skype para empresas y problemas de calidad y conexión de llamada de Teams de Microsoft. Le resultará útil para configurar las siguientes capacidades en Analytics llame al:
  
- Establecer los permisos que permiten a otro personal, como los agentes de asistencia técnica, use Analytics llamar pero evitar que accedan al resto de la Skype para el centro de administración de negocios. 
    
- Agregar creación, sitio e información del arrendatario a llamar Analytics cargando un archivo TSV o CSV de datos.
    
> [!NOTE]
> Análisis de llamada está en vista previa. Texto e imágenes que se describe aquí pueden no coincidir con su experiencia. 
  
## <a name="set-call-analytics-permissions"></a>Establecer permisos de llamar Analytics
<a name="BKMK_SetCAPerms"></a>

El usuario Admin, obtendrá acceso completo a todas las características de análisis llamar. Además, puede utilizar un modelo de asistencia técnica en llamar analítica que incluye grupos de permisos de nivel 1 y nivel 2. Los usuarios con permisos de nivel 1 pueden tener acceso a sólo una visión limitada de llamar Analytics. Los usuarios con permisos de nivel 2 pueden tener acceso a toda la funcionalidad de llamar Analytics. Dos niveles de permisos impiden el acceso al resto de la Skype para el centro de administración de negocios. Puede conceder acceso a los niveles mediante la adición de un grupo que contenga al usuario el nivel 1 o de la sección de nivel 2 de la página de permisos. Para obtener información detallada, vea [configurar permisos en niveles de llamar Analytics](set-up-call-analytics.md#BKMK_SetUpTier).
  
Los agentes de asistencia de nivel 1 controlen problemas básicos de calidad de la llamada. Agentes de nivel 1 no investigar los problemas con las reuniones; recopilan información relacionada y, a continuación, convertirse en un agente de nivel 2. Agentes de nivel 2 ver información en los registros de llamada detallados que está oculta de los agentes de nivel 1. En la tabla siguiente ofrece una visión general de la información disponible a agentes utilizando Analytics llamar.


|**Actividad**|**Información de análisis de llamada**|**Lo que ve el agente de nivel 1**|**Lo que ve el agente de nivel 2**|
|:-----|:-----|:-----|:-----|
|**Llamadas** <br/> |Nombre del llamador  <br/> |El nombre del usuario para el que busca en el agente.  <br/> |Nombre de usuario.  <br/> |
||Nombre del destinatario  <br/> |Se muestra como un usuario interno o externo.  <br/> |Nombre del destinatario.  <br/> |
||Número de teléfono del llamador  <br/> |Número de teléfono completo excepto los tres últimos dígitos están ofuscados con símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |Número de teléfono completo excepto los tres últimos dígitos están ofuscados con símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |
||Número de teléfono del destinatario  <br/> |Número de teléfono completo excepto los tres últimos dígitos están ofuscados con símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |Número de teléfono completo excepto los tres últimos dígitos están ofuscados con símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |
||**Detalles de llamadas** > ficha**Avanzadas** <br/> |Información que no se muestra.  <br/> |Todos los datos de muestra, como nombres de dispositivo, la dirección IP, la asignación de subred y mucho más.  <br/> |
||**Detalles de llamadas** > **Avanzadas** > ficha**Depurar** <br/> |Información que no se muestra.  <br/> |Todos los datos que se muestra como sufijo DNS y SSID.  <br/> |
|**Reuniones** <br/> |Nombres de los participantes  <br/> |El nombre del usuario para el que busca en el agente. Otros participantes identificados como usuario interno o externo.  <br/> |Todos los nombres que se muestran.  <br/> |
||Recuento de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalles de la sesión  <br/> |Detalles de la sesión se muestra con excepciones. Se muestra sólo el nombre del usuario para el que busca en el agente. Otros participantes identificados como usuario interno o externo. Los últimos tres dígitos de número de teléfono protegido con símbolos de asterisco.  <br/> |Detalles de la sesión que se muestra. Nombres de usuario y los detalles de la sesión que se muestra. Los últimos tres dígitos de número de teléfono protegido con símbolos de asterisco.  <br/> |
   
 **Configurar permisos en niveles de Analytics llamar** 
 <a name="BKMK_SetUpTier"> </a>
  
1. Crear grupos de seguridad de Office 365 para el nivel 1 y nivel 2 y agregue las personas que desee a cada grupo. También puede volver a grupos de seguridad existentes. Para obtener más información, vea [crear, modificar o eliminar un grupo de seguridad en el centro de administración de Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. En el centro de administración de Office 365, vaya a **centros de Admin** > **Skype para el negocio**.
    
    > [!NOTE]
    > Si aterrizar en el antiguo Skype para el centro de administración de negocios, vaya a la nueva versión haciendo clic en **ven a probar nuestro nuevo centro de admin**. 
  
3. En el nuevo Skype para el centro de administración de negocios, haga clic en **permisos**.
    
4. Agregue los grupos de seguridad de Office 365 a los cuadros de **nivel 1** y **nivel 2** . Puede agregar varios grupos para cada función.
    
     ![Captura de pantalla muestra los permisos de página llame Analytics con las opciones de permisos de nivel 1 y nivel 2.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Los usuarios con cualquiera de estos niveles de permiso obtener Analytics llame a través de la dirección URL dedicado *https://adminportal.services.skypeforbusiness.com*.
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Cargue un archivo TSV o CSV para agregar creación de sitio y la información de inquilinos
<a name="BKMK_UploadFiles"> </a>

Puede agregar información del arrendatario, sitio y edificio Analytics llamar cargando un archivo .csv o .tsv. Con toda esta información, llame a Analytics puede asignar direcciones IP a ubicaciones físicas. Usted o helpdesk agentes útil esta información ayudar a identificar tendencias en los problemas de la llamada. Por ejemplo, ¿por qué muchos de los usuarios en el mismo edificio tener similar llamar a problemas de calidad? 
  
![Captura de pantalla muestra la página de sitios con valores para el número de sitios y el número de subredes y el botón Seleccionar archivo para importar los datos del sitio cargando un .tsv o un archivo .csv.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Si eres un Skype para la administración de negocios, puede utilizar un archivo de datos existente desde el Skype para negocios en línea panel calidad llamar. En primer lugar, descargue el archivo desde el panel de calidad llamar y, a continuación, cargarlo en llamar Analytics. Para descargar un archivo de datos existente, vaya a la **Skype para el centro de administración de negocios** > **Herramientas** > **Skype para negocios en línea panel calidad llamar** > **Cargar ahora**. En la lista **Mis archivos** , haga clic en **Descargar** junto al archivo que desee.
  
Si está creando el archivo TSV o CSV desde el principio, vea [formato y estructura de archivos de datos de creación de archivos de datos de inquilinos](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Temas relacionados
<a name="BKMK_UploadFiles"> </a>

[Calidad de las llamadas uso llamar Analytics solucionar pobre Skype para empresas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[¿Cuál es la diferencia entre llamar a Analytics y llamar al panel de calidad?](difference-between-call-analytics-and-call-quality-dashboard.md)