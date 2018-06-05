---
title: Preparar Active Directory para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Resumen: Obtenga información sobre cómo preparar el dominio de Active Directory para una instalación de Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 0e031cc16bef00fc7b1ca8c2bd910fd0d36d5dde
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500994"
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Preparar Active Directory para Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo preparar el dominio de Active Directory para una instalación de Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype para Business Server trabaja estrechamente con Active Directory. Debe preparar el dominio de Active Directory para que funcione con Skype para Business Server. Este proceso se lleva a cabo en el Asistente para la implementación y se realiza sólo una vez para el dominio. Esto es debido a que el proceso crea grupos y modifica el dominio, y debe hacer que sólo una vez. Se pueden realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama. Preparación de Active Directory es el paso 4 de 8. Para obtener más información sobre la planeación de Active Directory, vea [requisitos de entorno para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![diagrama de información general](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar Active Directory

Skype para Business Server 2015 está integrada estrechamente con los servicios de dominio de Active Directory (AD DS). Antes de Skype para Business Server 2015 puede instalarse por primera vez, es preciso preparar Active Directory. La sección del Asistente para la implementación titulada **Preparar Active Directory** prepara el entorno de Active Directory para su uso con Skype para Business Server.
  
> [!NOTE]
> Skype para Business Server 2015 usa (AD DS) para realizar un seguimiento y comunicarse con todos los servidores en una topología. Cada servidor debe estar unido al dominio para que Skype para Business Server pueda funcionar correctamente. 
  
> [!IMPORTANT]
> Es necesario ejecutar el procedimiento de preparación de Active Directory solo una vez por cada dominio en la implementación. 
  
Vea los pasos del vídeo **Preparar Active Directory**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparar Active Directory desde el Asistente para la implementación

1. Inicie sesión como usuario con credenciales de administrador de esquema para el dominio de Active Directory.
    
2. Abra Skype para el Asistente para la implementación de servidor de negocio.
    
    > [!TIP]
    > Si desea revisar los archivos de registro que se crean mediante la Skype para el Asistente para la implementación de Business Server, se puede encontrar en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de AD DS que se ejecutó el paso. Por ejemplo, si el usuario inicia sesión como administrador de dominio en el dominio, contoso.local, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Haga clic en el vínculo **Preparar Active Directory**.
    
4. **Paso 1: Preparar el esquema**
    
    a. Haga clic en el menú desplegable debajo del título del paso 1 y revise la información sobre los requisitos previos para este paso.
    
    b. Haga clic en **Ejecutar** en el paso 1 a fin de iniciar el asistente para preparar el esquema.
    
    c. Recuerde que el procedimiento solo tiene que ejecutarse una vez por cada implementación; luego, haga clic en **Siguiente**.
    
    d. Una vez que haya preparado el esquema, puede ver el registro al hacer clic en **Ver registro**. 
    
    e. Haga clic en **Finalizar** y así cerrar el asistente para la preparación del esquema y regresar a los pasos para preparar Active Directory.
    
5. **Paso 2: Comprobar la replicación de la partición de esquema**
    
    a. Inicie sesión en el controlador de dominio para el dominio.
    
    b. Abra **Editar ADSI** desde el menú desplegable **Herramientas** en **Administrador de servidores**.
    
    c. En el menú **Acción**, haga clic en **Conectar con**.
    
    d. En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.
    
    e. En el contenedor de esquema, busque **CN=ms-RTC-SIP-SchemaVersion**. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o si el valor de los atributos **rangeUpper** y **rangeLower** es distinto de lo que se ha especificado, el esquema no se ha modificado o no se ha replicado.
    
6. **Paso 3: Preparar bosque actual**
    
    a. Haga clic en el menú desplegable debajo del título del paso 3 y revise la información sobre los requisitos previos para este paso.
    
    b. Haga clic en **Ejecutar** en el paso 3 a fin de iniciar el asistente para preparar el bosque actual.
    
    c. Recuerde que el procedimiento solo tiene que ejecutarse una vez por cada implementación; luego, haga clic en **Siguiente**.
    
    d. Especifique el dominio donde se crearán los grupos universales. Si el servidor es parte del dominio, puede seleccionar **Dominio local** y hacer clic en **Siguiente**.
    
    e. Una vez que haya preparado el bosque, puede ver el registro al hacer clic en **Ver registro**. 
    
    f. Haga clic en **Finalizar** y así cerrar el asistente para la preparación del bosque actual y regresar a los pasos para preparar Active Directory.
    
    g. Haga clic en **Skype para Shell de administración de servidor empresarial** desde la página de **aplicaciones** para iniciar PowerShell.
    
    h. Escriba el comando Get-CsAdForest y presione **ENTRAR**.
    
    . Si el resultado es **LC_FORESTSETTINGS_STATE_READY**, el bosque ha se ha preparado correctamente, tal como se muestra en la ilustración.
    
     ![Verifique la replicación del bosque.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Paso 4: Comprobar la replicación del catálogo global**
    
    a. En un controlador de dominio (preferentemente en un sitio remoto desde otros controladores de dominio) en el bosque donde se ejecutó la preparación del bosque, abra **Usuarios y equipos de Active Directory**.
    
    b. En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.
    
    c. Haga clic en el contenedor **Usuarios** del panel izquierdo y busque el grupo universal **CsAdministrator** en el panel derecho. Si CsAdministrator (entre los otros grupos universales nuevos que empiezan con Cs) está presente, la replicación de Active Directory se ha realizado correctamente.
    
    d. Si los grupos aún no están presentes, puede forzar la replicación o esperar 15 minutos y actualizar el panel derecho. Cuando los grupos están presentes, la replicación se ha completado.
    
8. **Paso 5: Preparar el dominio actual**
    
    a. Revise la información sobre los requisitos previos para el paso 5.
    
    b. Haga clic en **Ejecutar** en el paso 5 a fin de iniciar el asistente para preparar el dominio actual.
    
    c. Recuerde que el procedimiento solo tiene que ejecutarse una vez por cada dominio en la implementación; luego, haga clic en **Siguiente**.
    
    d. Una vez que haya preparado el dominio, puede ver el registro al hacer clic en **Ver registro**. 
    
    e. Haga clic en **Finalizar** y así cerrar el asistente para la preparación del dominio actual y regresar a los pasos para preparar Active Directory.
    
    Estos pasos deben realizarse en cada dominio donde Skype para los objetos Business Server se encuentran, en caso contrario, los servicios es posible que no se inicie. Dichos objetos incluyen todo tipo de objetos de Active Directory, como usuarios, objetos de contacto, grupos administrativos o todo otro tipo de objeto. Puede usar Set-CsUserReplicatorConfiguration - ADDomainNamingContextList para agregar solo los dominios con Skype para objetos de servidor empresarial, si es necesario.
    
9. **Paso 6: Comprobar la replicación en el dominio**
    
    a. Haga clic en **Skype para Shell de administración de servidor empresarial** desde la página de **aplicaciones** para iniciar PowerShell.
    
    b. Use el comando Get-CsAdDomain para comprobar la replicación dentro del dominio.
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > Si no especifica el parámetro de dominio, el valor se configura con el dominio local. 
  
    Ejemplo de la ejecución del comando para el dominio contoso.local:
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > El uso del parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se guarda en el contenedor del sistema (habitual en implementaciones de actualización cuya configuración global no se ha migrado al contenedor de configuración), necesitará definir un controlador de dominio en la raíz del bosque de AD DS. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet da por sentado que la configuración se guarda en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory. 
  
    c. Si el resultado es **LC_DOMAINSETTINGS_STATE_READY**, el dominio se ha replicado correctamente.
    
10. **Paso 7: Agregar usuarios para proporcionar acceso administrativo a la Skype para el Panel de Control de servidor empresarial**
    
    a. Inicie sesión como miembro del grupo Administradores del dominio o del grupo RTCUniversalServerAdmins.
    
    b. Abra **Usuarios y equipos de Active Directory**, expanda el dominio, haga clic en el contenedor **Usuarios**, haga clic con el botón secundario en CSAdministrator y seleccione **Propiedades**.
    
    c. En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.
    
    d. En la pestaña **Miembros**, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.
    
    e. En la pestaña **Miembros**, confirme que estén los usuarios o los grupos que haya seleccionado. Haga clic en **Aceptar**.
    
    > [!CAUTION]
    > El Skype para el Panel de Control de servidor empresarial es una herramienta de control de acceso basado en roles. Pertenencia al grupo CsAdministrator proporciona a un usuario que está usando el Skype para control total del Panel de Control de servidor empresarial para todas las funciones de configuración disponibles. Hay otros roles disponibles diseñados para funciones específicas. Para obtener información detallada sobre las funciones disponibles, vea [requisitos de entorno para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Tenga en cuenta que los usuarios no tienen a habilitarse para Skype para Business Server con el fin de hacerse miembros de los grupos de administración. 
  
    > [!CAUTION]
    > Para ayudar a mantener la seguridad y la integridad del control de acceso basado en roles, agregar usuarios a los grupos que definen qué rol realiza el usuario en administración de la Skype para la implementación de Business Server. 
  
11. Cierra la sesión y, a continuación, vuelva a iniciar sesión Windows para que el token de seguridad se ha actualizado con el nuevo Skype para el grupo de seguridad de Business Server y, a continuación, vuelva a abrir al Asistente para la implementación.
    
12. Compruebe que haya una marca de verificación verde junto a **Preparar Active Director** para comprobar que la acción se realizó correctamente, tal como se muestra en la figura.
    
     ![Preparación de Active Directory completada.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Vea también
 
[Servicios de dominio de Active Directory para Skype para Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)