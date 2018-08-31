---
title: Configurar el análisis de llamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Configurar y usar el análisis de llamada para identificar y solucionar problemas de Skype para profesionales y Microsoft Teams problemas de calidad de llamada.
ms.openlocfilehash: d2e4a603010f668fa0b9a2767b1580d4b9b71a47
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23784881"
---
# <a name="set-up-call-analytics"></a>Configurar el análisis de llamadas

Como un Skype para administración en línea de negocio, puede usar el análisis de llamadas para solucionar problemas de Skype para la empresa y Microsoft Teams llamar a problemas de calidad y de conexión. Es posible que encuentre útil para configurar las siguientes funciones en análisis de llamadas:
  
- Establecer los permisos que permiten a otros personal, por ejemplo, los agentes del departamento de soporte técnico, use llamar análisis pero impedir que obtener acceso al resto de la Skype para el centro de administración de negocio. 
    
- Agregar información del inquilino, de sitio y de creación para llamar a análisis al cargar un archivo de datos .tsv o .csv.
    
**Análisis de llamada está ahora disponible en el Microsoft Teams y Skype para el centro de administración de negocio.** Para ver toda la información de la llamada y los datos para un usuario, utilice la ficha **Historial de llamadas** . Para ello, puede buscar en la página de perfil del usuario buscando el usuario desde el panel o buscar el usuario de **los usuarios** en el panel de navegación izquierdo.

> [!IMPORTANT]
> Permisos de agente de departamento de soporte técnico y la carga de la topología de red estará disponibles en el nuevo portal de administración en los próximos meses. Mientras tanto, puede seguir usando https://adminportal.services.skypeforbusiness.com para el acceso de departamento de soporte técnico de nivel 1 y nivel 2.
  
## <a name="set-call-analytics-permissions"></a>Establecer permisos de análisis de llamadas
<a name="BKMK_SetCAPerms"></a>

Como la administración, obtener acceso completo a todas las características de análisis de llamadas. Además, puede usar un modelo de departamento de soporte técnico en análisis de llamadas que incluye los grupos de permisos de nivel 1 y nivel 2. Los usuarios con permisos de nivel 1 pueden obtener acceso sólo una vista limitada del análisis de llamadas. Los usuarios con permisos de nivel 2 pueden tener acceso a la funcionalidad completa de análisis de llamadas. Ambos niveles de permisos impiden el acceso al resto de la Microsoft Teams y Skype para el centro de administración de negocio. Puede conceder acceso a los niveles mediante la adición de un grupo que contiene el usuario para el nivel 1 o la sección de nivel 2 de la página de permisos. Para obtener información detallada, vea [configurar permisos en niveles en el análisis de llamadas](set-up-call-analytics.md#BKMK_SetUpTier).
  
Los agentes del departamento de soporte técnico de nivel 1 controlan problemas básicos de calidad de la llamada. Los agentes de nivel 1 no investigar problemas con reuniones; puedan recopilan información relacionada y, a continuación, pasar a un agente de nivel 2. Los agentes de nivel 2 ver información en el registro de llamadas detallada que está oculto de agentes de nivel 1. En la siguiente tabla proporciona una visión general de la información disponible a agentes mediante el análisis de llamadas.


|**Actividad**|**Información de análisis de llamada**|**Lo que ve el agente de nivel 1**|**Lo que ve el agente de nivel 2**|
|:-----|:-----|:-----|:-----|
|**Llamadas** <br/> |Nombre del autor de la llamada  <br/> |El nombre del usuario para el que desea buscar el agente.  <br/> |Nombre de usuario.  <br/> |
||Nombre del destinatario  <br/> |Se muestra como usuario interno o externo.  <br/> |Nombre del destinatario.  <br/> |
||Número de teléfono del autor de la llamada  <br/> |Número de teléfono completo, excepto los últimos tres dígitos son confusos con los símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |Número de teléfono completo, excepto los últimos tres dígitos son confusos con los símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |
||Número de teléfono del destinatario  <br/> |Número de teléfono completo, excepto los últimos tres dígitos son confusos con los símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |Número de teléfono completo, excepto los últimos tres dígitos son confusos con los símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |
||**Detalles de llamadas** > ficha**Opciones avanzadas** <br/> |Información que no se muestra.  <br/> |Todos los detalles que se muestran, como los nombres de dispositivo, dirección IP, asignación de subred y mucho más.  <br/> |
||**Detalles de llamadas** > **Avanzadas** > ficha**Depurar** <br/> |Información que no se muestra.  <br/> |Todos los detalles que se muestran como sufijo DNS y SSID.  <br/> |
|**Reuniones.** <br/> |Nombres de los participantes  <br/> |El nombre del usuario para el que desea buscar el agente. Demás participantes identificados como usuario interno o externo.  <br/> |Todos los nombres que se muestran.  <br/> |
||Recuento de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalles de la sesión  <br/> |Detalles de la sesión se muestra con excepciones. Se muestra sólo el nombre del usuario para el que desea buscar el agente. Demás participantes identificados como usuario interno o externo. Los últimos tres dígitos del número de teléfono confusos con los símbolos de asterisco.  <br/> |Detalles de la sesión que se muestra. Los nombres de usuario y se muestra detalles de la sesión. Los últimos tres dígitos del número de teléfono confusos con los símbolos de asterisco.  <br/> |
   
 **Configurar permisos en niveles de análisis de llamadas de** 
 <a name="BKMK_SetUpTier"> </a>

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**
  
1. Creación de grupos de seguridad de Office 365 para nivel 1 y nivel 2, y agregue las personas que desee a cada grupo. También puede volver a usar los grupos de seguridad existentes. Para obtener más información, vea [crear, editar o eliminar un grupo de seguridad en el centro de administración de Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. En el centro de administración de Office 365, vaya a **centros de administración** > **Skype para la empresa**.

    > [!NOTE]
    > Si se encuentra en los **equipos de Microsoft y Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, haga clic en **portal heredado**.
  
3. En el **Análisis de llamadas (vista previa)**, haga clic en **permisos**.
    
4. Agregue los grupos de seguridad de Office 365 a los cuadros de **nivel 1** y **nivel 2** . Puede agregar varios grupos a cada rol.
    
     ![Captura de pantalla muestra la página permisos para llamar a análisis con las opciones de permisos de nivel 1 y nivel 2.](media/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Obtienen los usuarios con cualquiera de estos niveles de permisos para llamar a análisis a través de la dirección URL dedicada *https://adminportal.services.skypeforbusiness.com*.
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Cargue un archivo .tsv o .csv para agregar la creación de sitios y la información de inquilinos
<a name="BKMK_UploadFiles"> </a>

Puede agregar información del inquilino, de sitio y de creación para análisis de llamar a cargar un archivo .csv o .tsv. Con toda esta información, llame al análisis puede asignar direcciones IP a ubicaciones físicas. Usted o departamento de soporte técnico los agentes pueden encontrar esta información útil para ayudar a las tendencias de manchas de color en problemas de llamada. Por ejemplo, ¿por qué son similares de muchos usuarios en el mismo edificio tener llamar a problemas de calidad? 
  
![Captura de pantalla muestra la página de sitios con los valores de número de sitios y el número de subredes y el botón Seleccionar archivo para importar datos del sitio mediante la carga de un .tsv o un archivo .csv.](media/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Si usted es un Skype para administración empresarial, puede usar un archivo de datos existente desde el Skype para profesionales Online panel calidad de llamadas. En primer lugar, descargue el archivo desde el panel de calidad de llamadas y, a continuación, cárguela en análisis de llamadas. Para descargar un archivo de datos existente, vaya a la **Skype para el centro de administración de negocio de** > **Herramientas** > **Skype para profesionales Online panel calidad de llamadas** > **Cargar ahora**. En la lista **Mis cargas** , haga clic en **Descargar** junto al archivo que desee.
  
Si está creando el archivo .tsv o .csv desde el principio, vea [formato y estructura de archivos de datos de creación de archivos de datos de inquilinos](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Temas relacionados
<a name="BKMK_UploadFiles"> </a>

[Usar Análisis de llamadas para solucionar problemas de mala calidad de llamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamada y el panel de calidad de llamada](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
