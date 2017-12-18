---
title: "Configurar Skype para Business Analytics de llamadas"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
description: "Set up and use Call Analytics to identify and troubleshoot Skype for Business and Microsoft Teams call quality problems."
---

# Configurar Skype para Business Analytics de llamadas

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Como administrador de Skype Empresarial Online, puede usar análisis llamar para solucionar problemas de conexión y la calidad de llamada Skype Empresarial y Microsoft Teams. Es posible que le resulte útil para configurar las siguientes capacidades de análisis de llamadas:
  
- Establecer permisos que permitir que los demás personal, como agentes de departamento de soporte técnico, utilizan el análisis de llamar pero impiden que tener acceso al resto del centro de administración de Skype Empresarial.
    
- Agregar información de inquilino, sitios y creación para el análisis de llamar al cargar un archivo de datos .tsv o .csv.
    
> [!NOTE]
> Análisis de llamada está en vista previa. Texto e imágenes que se describen aquí no pueden coincidir con su experiencia. 
  
## Establecer permisos de análisis de llamadas
<a name="BKMK_SetCAPerms"> </a>

Como administrador, obtendrá acceso completo a todas las características de análisis de llamadas. Además, puede usar un modelo de departamento de soporte técnico en análisis de llamadas que incluye los grupos de permisos de nivel 1 y nivel 2. Los usuarios con permisos de nivel 1 pueden tener acceso a solo una vista limitada del análisis de llamadas. Los usuarios con permisos de nivel 2 pueden tener acceso a la funcionalidad completa de análisis de llamadas. Dos niveles de permisos impiden el acceso al resto del centro de administración de Skype Empresarial. Puede conceder acceso a los niveles mediante la adición de un grupo que contiene el usuario para el nivel 1 o de la sección de nivel 2 de la página de permisos. Para obtener información detallada, vea [configurar permisos en niveles de análisis de llamadas](fbf7247a-84ae-46cc-9204-2c45b1c734cd.md#BKMK_SetUpTier).
  
Agentes del departamento de soporte técnico de nivel 1 identificador básicas problemas de calidad de la llamada. Agentes de nivel 1 no investigar problemas con las reuniones; se recopila información relacionada y, a continuación, escalar a un agente de nivel 2. Agentes de nivel 2 ver información en registros de llamadas detallada que está oculta agentes de nivel 1. En la tabla siguiente proporciona una descripción general de la información disponible a agentes mediante análisis de llamadas.
  
|
|
|**Actividad**|**Información de análisis de llamada**|**Lo que ve el agente de nivel 1**|**Lo que ve el agente de nivel 2**|
|:-----|:-----|:-----|:-----|
|**Llamadas** <br/> |Nombre del autor de la llamada  <br/> |El nombre del usuario para el que se busca el agente.  <br/> |Nombre de usuario.  <br/> |
||Nombre del destinatario  <br/> |Se muestra como un usuario interno o externo.  <br/> |Nombre del destinatario.  <br/> |
||Número de teléfono de llamada  <br/> |Número de teléfono completo excepto los últimos tres dígitos está protegido con símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |Número de teléfono completo excepto los últimos tres dígitos está protegido con símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |
||Número de teléfono del destinatario  <br/> |Número de teléfono completo excepto los últimos tres dígitos está protegido con símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |Número de teléfono completo excepto los últimos tres dígitos está protegido con símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |
||**Detalles de llamadas** > pestaña **Avanzadas** <br/> |No se muestra la información.  <br/> |Todos los detalles que se muestra, por ejemplo, nombres de dispositivo, la dirección IP, la asignación de subred y más.  <br/> |
||**Detalles de llamadas** > **Avanzadas** > ficha **Depurar** <br/> |No se muestra la información.  <br/> |Todos los detalles que se muestra como sufijo DNS y SSID.  <br/> |
|**Reuniones** <br/> |Nombres de los participantes  <br/> |El nombre del usuario para el que se busca el agente. Otros participantes identificados como usuario interna o externa.  <br/> |Todos los nombres que se muestran.  <br/> |
||Recuento de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalles de la sesión  <br/> |Detalles de la sesión que se muestra con las excepciones. El nombre del usuario para el que se muestra el agente de la búsqueda. Otros participantes identificados como usuario interna o externa. Últimos tres dígitos del número de teléfono protegido con símbolos de asterisco.  <br/> |Detalles de la sesión que se muestra. Nombres de usuario y se muestra detalles de la sesión. Últimos tres dígitos del número de teléfono protegido con símbolos de asterisco.  <br/> |
   
 **Configurar permisos en niveles de análisis de llamadas**
  
1. Crear grupos de seguridad de Office 365 de nivel 1 y nivel 2 y agregue las personas que desea para cada grupo. También puede volver a usar los grupos de seguridad existentes. Para obtener más información, vea [Crear, editar o eliminar un grupo de seguridad en el centro de administración de Office 365](http://technet.microsoft.com/library/55c96b32-e086-4c9e-948b-a018b44510cb%28Office.14%29.aspx).
    
2. En la Centro de administración de Office 365, vaya a **los centros de administración** > **Skype empresarial**.
    
    > [!NOTE]
    > Si land en el centro de administración de Skype Empresarial antiguo, vaya a la nueva versión haciendo clic en **vienen Pruebe nuestro centro de administración de nuevo**. 
  
3. En el centro de administración de Skype Empresarial nuevo, haga clic en **permisos**.
    
4. Agregue los grupos de seguridad de Office 365 en los cuadros de **nivel 1** y **nivel 2**. Puede agregar varios grupos a cada rol.
    
     ![Screenshot shows the Permissions for Call Analytics page with the options for Tier 1 and Tier 2 permissions.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
Los usuarios con uno de estos niveles de permisos ir a análisis de llamar a través de la https://adminportal.services.skypeforbusiness.com URL dedicado.
  
## Cargar un archivo .csv o de .tsv para agregar la creación de sitios y la información de inquilinos
<a name="BKMK_UploadFiles"> </a>

Puede agregar información de inquilino, sitios y creación para el análisis de llamar al cargar un archivo .csv o .tsv. Con toda esta información, llamada análisis puede asignar direcciones IP y las ubicaciones físicas. Usted o departamento de soporte técnico agentes útil esta información ayudar a detectar tendencias de problemas de la llamada. Por ejemplo, ¿por qué son similares de muchos usuarios en el mismo edificio tener llamar a problemas de calidad?
  
![Screenshot shows the Sites page with values for Number of sites and Number of subnets, and the Select file button to import site data by uploading a .tsv or a .csv file.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Si es un administrador de Skype Empresarial, puede usar un archivo de datos existente desde el panel de calidad de llamada Skype Empresarial Online. En primer lugar, descargue el archivo desde el panel de calidad de llamada y, a continuación, cargar para el análisis de llamar. Para descargar un archivo de datos existente, vaya a la **Skype centro de administración de negocio** > **Herramientas** > **Skype para Business Online panel calidad de llamadas** > **Cargar ahora**. En la lista **Mis cargas**, haga clic en **Descargar** junto al archivo que desee.
  
Si está creando el archivo .csv o de .tsv desde cero, vea [Formato del archivo de datos del inquilino y la estructura del archivo de datos Compilación](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_TenantDataFile).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Calidad de llamadas de análisis de uso llamar a solucionar problemas de una mala Skype para la empresa](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md)
  
[¿Cuál es la diferencia entre el análisis de llamadas y panel de calidad de llamada?](what-s-the-difference-between-call-analytics-and-call-quality-dashboard.md)

