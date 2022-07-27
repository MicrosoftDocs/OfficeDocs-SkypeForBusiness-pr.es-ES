---
title: Configurar entrenador profesional para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar y hacer que el Entrenador profesional esté disponible para Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
ms.custom:
- admindeeplinkTEAMS
- admindeeplinkMAC
appliesto:
- Microsoft Teams
ms.openlocfilehash: f162b4dc15a2c0b776ba3c9c3b0df8ac0ed2ce87
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024196"
---
# <a name="set-up-and-configure-career-coach-for-microsoft-teams"></a>Configurar entrenador profesional para Microsoft Teams

Este artículo es para administradores de TI de educación superior para aprender a configurar Entrenador profesional para Microsoft Teams.

Los pasos principales para configurar, configurar y publicar el Entrenador profesional son:

1. [Paso 1: Prepare su inquilino para entrenador profesional](#step-1-prepare-your-microsoft-365-tenant-for-career-coach).
1. [Paso 2: Comprar licencias de Entrenador profesional](#step-2-purchase-career-coach-licenses).
1. [Paso 3: Acceder a la configuración del Entrenador profesional](#step-3-access-the-career-coach-app-settings).
1. [Paso 4: Configurar las opciones de Entrenador profesional](#step-4-configure-career-coach-settings).
1. [Paso 5: Haga que el Entrenador profesional esté disponible para su institución](#step-5-make-career-coach-available-to-your-institution).

## <a name="identify-roles-and-permissions"></a>Identificar roles y permisos

Configurar el Entrenador profesional requiere varios tipos de roles de administrador. Estos roles y permisos pueden asignarse a una persona o pueden requerir la colaboración con profesionales de TI de su institución educativa. Use la lista de comprobación siguiente para identificar a las personas necesarias para completar las tareas a las que se hace referencia.

Puede comprobar los roles asignados a su cuenta visitando la [Centro de administración de Microsoft 365 > Usuarios > Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822) > Seleccione su nombre de usuario para confirmar su rol.

Obtenga más información sobre [los roles de administrador en la Centro de administración de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

### <a name="microsoft-365-admin-center-tasks"></a>[Centro de administración de Microsoft 365 tareas](https://go.microsoft.com/fwlink/p/?linkid=2024339)

Rol: [Administrador global](/azure/active-directory/roles/permissions-reference#global-administrator)

Tareas de Entrenador profesional:

- [Comprar licencias](#step-2-purchase-career-coach-licenses).
- [Asignar licencias](#assign-career-coach-licenses-to-users).

### <a name="azure-active-directory-admin-center-tasks"></a>[Tareas del centro de administración de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=2067268)

Rol: [Administrador global](/azure/active-directory/roles/permissions-reference#global-administrator)

Tarea de Entrenador profesional:

- [Active las conexiones de la cuenta de LinkedIn](#turn-on-linkedin-account-connections).

### <a name="teams-admin-center-tasks"></a>[Tareas del centro de administración de Teams](https://admin.teams.microsoft.com/dashboard)

Rol: [Administrador de Teams](/azure/active-directory/roles/permissions-reference#teams-administrator)

Tareas de Entrenador profesional:

- [Agregue entrenador profesional como una aplicación instalada](#add-career-coach-as-an-installed-app).
- [Configure las opciones de la aplicación Entrenador profesional](#step-4-configure-career-coach-settings).
- [Configurar directivas](#identify-roles-and-permissions).
- [Ancla la aplicación](#identify-roles-and-permissions).

### <a name="linkedin-developer-portal-tasks"></a>Tareas del portal para desarrolladores de LinkedIn

Rol: [Super Administración de página escolar de LinkedIn](https://www.linkedin.com/help/linkedin/answer/a541981)

Tarea de Entrenador profesional:

- [Compruebe la página de LinkedIn School](#verify-the-linkedin-school-page).

## <a name="prepare-for-career-coach"></a>Prepararse para entrenador profesional

Antes de configurar y configurar entrenador profesional, siga estos pasos de preparación.

1. [Paso 1: Prepare su inquilino para entrenador profesional](#step-1-prepare-your-microsoft-365-tenant-for-career-coach).
1. [Paso 2: Comprar licencias de Entrenador profesional](#step-2-purchase-career-coach-licenses).

### <a name="step-1-prepare-your-microsoft-365-tenant-for-career-coach"></a>Paso 1: Preparar el inquilino de Microsoft 365 para el Entrenador profesional

#### <a name="turn-on-linkedin-account-connections"></a>Activar las conexiones de la cuenta de LinkedIn

Hay dos formas en las que el Entrenador profesional usa las conexiones de la cuenta de LinkedIn:

- Para permitir que los estudiantes, los profesores y el personal conecten su cuenta de Microsoft 365 a su cuenta de LinkedIn y [envíen invitaciones de LinkedIn desde el Entrenador profesional](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_connect_your_linkedin_account).
- Para activar las características [Crear su red](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_build_your_network) y [Explorar carreras](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_discover_your_career_path) con datos de antiguos alumnos públicos de LinkedIn.

Para activar las conexiones de la cuenta de LinkedIn:

1. Inicie sesión en el [Centro de administración de Azure AD](https://go.microsoft.com/fwlink/p/?linkid=2067268) con una [cuenta de administrador global](#identify-roles-and-permissions) para la organización de Azure AD.

2. Seleccione **Usuarios**.

3. En la página **Usuarios** , seleccione **Configuración de usuario**.

4. Las **conexiones de la cuenta de LinkedIn** deben establecerse en **Sí** o **Grupo seleccionado** para que el Entrenador profesional esté correctamente configurado.

   - Seleccione **Sí** para activar el servicio para todos los usuarios de su institución educativa.
   - Seleccione **Grupo seleccionado** para activar el servicio solo para un grupo de usuarios seleccionados de su institución educativa.

Para obtener más información, consulte [Conexiones de cuentas de LinkedIn en Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration).

> [!NOTE]
> No se comparten datos sin el consentimiento del usuario.

#### <a name="allow-microsoft-apps-in-teams"></a>Permitir aplicaciones de Microsoft en Teams

El Entrenador profesional es una aplicación de Microsoft, por lo que debe estar permitido dentro de las directivas de permisos de la aplicación teams.

1. Inicie sesión en el **[Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. En el panel de navegación izquierdo, seleccione **Directivas****[de permisos](https://admin.teams.microsoft.com/policies/manage-apps)** de aplicaciones  >  de Teams.

3. Seleccione la directiva que prefiera.
    1. Si no está seguro de qué directiva usar, consulte la documentación  de administración de directivas de [Microsoft Teams](policy-packages-edu.md)o use el [Asistente para](easy-policy-setup-edu.md) directivas de educación para configurar una directiva para Microsoft Teams.

Obtenga más información sobre [cómo configurar directivas de permisos](teams-app-permission-policies.md).

#### <a name="add-career-coach-as-an-installed-app"></a>Agregar entrenador profesional como una aplicación instalada

Este paso garantiza que el Entrenador profesional esté correctamente configurado para su institución y que los alumnos puedan encontrarlo.

1. Inicie sesión en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).

2. Seleccione **Directivas** **de configuración de** aplicaciones  > de Teams y seleccione la directiva que prefiera.
    1. Si no está seguro de qué directiva usar, consulte la documentación  de administración de directivas de [Microsoft Teams](policy-packages-edu.md)o use el [Asistente para](easy-policy-setup-edu.md) directivas de educación para configurar una directiva para Microsoft Teams.

3. En **Aplicaciones instaladas**, selecciona  **+ Agregar aplicaciones**.

4. En el panel **Agregar aplicaciones instaladas** , busque las aplicaciones que desea instalar automáticamente para los usuarios cuando inicien Teams. También puede filtrar aplicaciones por directiva de permisos de aplicaciones.

5. Cuando hayas elegido la lista de aplicaciones, selecciona **Agregar**.

6. Selecciona  **Guardar** > **Confirmar**.

Editar o asignar una directiva puede tardar unas horas en surtir efecto. El Entrenador profesional no estará disponible en Microsoft Teams hasta que se completen los cambios.

### <a name="step-2-purchase-career-coach-licenses"></a>Paso 2: Comprar licencias de Entrenador profesional

#### <a name="license-types"></a>Tipos de licencia

El Entrenador profesional requiere una licencia para acceder a la aplicación.

Hay dos tipos de licencia disponibles.

- La **licencia de Estudiante** está diseñada para los alumnos.
- La **licencia para profesores** está diseñada para profesores, personal y profesionales de TI involucrados en apoyar a los estudiantes con el Entrenador profesional.
  - Se debe asignar al administrador de TI una licencia de entrenador profesional para **profesores** que complete la configuración.

#### <a name="purchase-licenses"></a>Comprar licencias

Entrenador profesional está disponible en todo el mundo (excepto China y Rusia) para instituciones de educación superior cualificadas como una licencia complementaria a través de inscripción para soluciones educativas (EES), proveedores de servicios en la nube (CSP) y Centro de administración de Microsoft 365 (web directo).

Como aplicación de Microsoft Teams, el inquilino debe tener Microsoft 365 A3/A5 o Office 365 A1/A3/A5 para comprar la licencia de Entrenador profesional adicional. Se ofrecen licencias independientes para estudiantes y usuarios de profesores.

#### <a name="sign-up-for-a-free-trial"></a>Registrarse para obtener una prueba gratuita

Una prueba gratuita de 90 días estándar está disponible para 25 estudiantes y 25 licencias para profesores. Hay una versión de prueba disponible por inquilino válido. Los inquilinos cualificados para comprar licencias de Entrenador profesional pueden activar licencias de prueba desde Centro de administración de Microsoft 365.

Para la activación de la versión de prueba, inicie sesión en [Centro de administración de Microsoft 365 > servicios de facturación > Compra > busque Entrenador](https://go.microsoft.com/fwlink/p/?linkid=868433) profesional para encontrar la prueba de [licencia para estudiantes](https://signup.microsoft.com/signup?OfferId=b3a40ff2-3d0d-481e-a0ed-f4de1069f201) y la [prueba de licencia para profesores](https://signup.microsoft.com/signup?OfferId=6f6e7db5-b9ab-4baa-86be-f13d0ae6a2c8).

## <a name="set-up-and-configure-career-coach-settings"></a>Configurar y configurar opciones de Entrenador profesional

Para configurar y configurar las opciones de Entrenador profesional para su institución, siga estos pasos.

1. [Paso 3: Acceder a la configuración de la aplicación Entrenador profesional](#step-3-access-the-career-coach-app-settings).
1. [Paso 4: Configurar las opciones de Entrenador profesional](#step-4-configure-career-coach-settings).

### <a name="step-3-access-the-career-coach-app-settings"></a>Paso 3: Acceder a la configuración de la aplicación Entrenador profesional

Para configurar las opciones del Entrenador profesional y permitirla para los usuarios, debe ser administrador global o administrador del servicio de Teams para poder acceder a la página.

1. Inicie sesión en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. En el panel de navegación izquierdo, seleccione Aplicaciones  > **de Teams** **Administrar aplicaciones**.
3. Busque o busque **Entrenador profesional**.
4. Seleccione **Entrenador profesional** y, después, **Configuración**.

![Captura de pantalla que muestra la aplicación Entrenador profesional seleccionada con la pestaña Configuración seleccionada.](media/career-coach-app-updated.png)

### <a name="step-4-configure-career-coach-settings"></a>Paso 4: Configurar las opciones de Entrenador profesional

Para configurar el Entrenador profesional para estudiantes, profesores y personal, se requieren las siguientes opciones de configuración.

- [Marca y preferencias](#brand-and-preferences)
- [Conexión de LinkedIn](#linkedin-connection)
- [Catálogo de cursos](#course-catalog)
- [Campos de estudio](#fields-of-study)

También puede establecer opciones de [personalización](#customization-options) opcionales.

#### <a name="brand-and-preferences"></a>Marca y preferencias

Personalice entrenador profesional para que coincida con la marca de su institución educativa. Usted es responsable de respetar los derechos de otros, incluidos los derechos de autor y marca comercial.

> [!IMPORTANT]
> Esta es una sección obligatoria. El Entrenador profesional no se puede activar sin enviar **la marca y las preferencias** .

1. Inicie sesión en el **[Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Seleccione **Aplicaciones** >  de Teams **Administrar aplicaciones** > **Configuración del** > **entrenador** >  profesional **Editar marca y preferencias**.

3. En **Personalización de marca**, agregue **Nombre de la organización**.

4. Cargue el **icono Organización**. El icono se usa en todo el Entrenador profesional para identificar contenido exclusivo de su institución educativa, recursos del catálogo de cursos en toda la aplicación y en la sección de experiencias del mundo real del panel.

    El icono tiene el siguiente formato:

    - Png transparente
    - Relación de aspecto de 1:1
    - Tamaño máximo de 64 px x 64 px

5. Cargue la **imagen en miniatura del contenido de aprendizaje**. La miniatura se usará para los recursos de aprendizaje del catálogo de cursos en toda la aplicación cuando no se especifique una imagen específica para un curso ofrecido por su institución educativa.

    El formato de la miniatura es el siguiente:

    - UN ARCHIVO PNG
    - Relación de aspecto de 16:9
    - Tamaño máximo de 360 px x 200 px

6. Este paso es opcional. Agregue la **dirección URL de la directiva de privacidad de la organización**. Si se agrega, la directiva de privacidad de la institución estará disponible para que los alumnos la revisen en el Entrenador profesional.

7. Selecciona **Enviar**.

8. Para confirmar que la configuración se ha enviado correctamente, compruebe [el estado de configuración del Entrenador](#configuration-status) profesional para **Completar**.

![Captura de pantalla que muestra la sección de personalización de marca de Entrenador profesional del centro de administración.](media/career-coach-brand-updated.png)

#### <a name="linkedin-connection"></a>Conexión de LinkedIn

La configuración de conexión de LinkedIn conecta al Entrenador profesional con datos de antiguos alumnos públicos de la página de la escuela de LinkedIn de su institución.

Este paso solo se puede completar si [las conexiones de la cuenta de LinkedIn están habilitadas en Azure Active Directory](#turn-on-linkedin-account-connections). La configuración de conexión de LinkedIn activa las características [Crear su red](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_build_your_network) y [Explorar carreras](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_discover_your_career_path) .

> [!IMPORTANT]
> Esta es una sección obligatoria. El Entrenador profesional no se puede activar sin la conexión de la página educativa de LinkedIn verificada.

##### <a name="add-the-linkedin-school-page-url"></a>Agregar la dirección URL de la página educativa de LinkedIn

El proceso de agregar la dirección URL de la página educativa de LinkedIn es controlado por un administrador de Teams. El paso posterior de comprobar la dirección URL lo completa el superadministrador de páginas de la escuela de LinkedIn de su institución educativa.

1. Inicie sesión en el **[Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Seleccione **Aplicaciones** >  de Teams **Administrar aplicaciones** > **Configuración del** > **Entrenador** >  profesional **conexión de LinkedIn**.

3. Seleccione **Conectarse a LinkedIn**.

4. Busque la página educativa de LinkedIn de su institución buscando en LinkedIn y seleccionando el filtro **Escuela** . También puede ponerse en contacto con un miembro del personal de marketing de su institución para determinar la página educativa de LinkedIn correcta que se usará. Para obtener más información, consulte [Cómo identificar páginas de LinkedIn](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en).

    ![Captura de pantalla que muestra la búsqueda de LinkedIn para la escuela.](media/career-coach-school-search-updated.png)

5. Agregue la **dirección URL de la página educativa de LinkedIn**. La dirección URL debe ser una *página educativa*, no una *página de empresa* y normalmente tiene el formato `https://www.linkedin.com/school/willow-university/`.

   ![Captura de pantalla que muestra el ejemplo de página de LinkedIn School.](media/career-coach-linkedin-page-url-updated.png)

6. Selecciona **Enviar**.

7. Una vez **que la dirección URL de la página educativa de LinkedIn** se haya enviado correctamente, la página de configuración se actualizará para mostrar el  **vínculo** de verificación y la  **expiración del vínculo de verificación**. El vínculo de verificación expira después de 30 días.

8. Copie el **vínculo verificación** y compártalo con el superadministrador de la página de la escuela de LinkedIn de su institución educativa.

9. El superadministrador de la página educativa de LinkedIn usará el vínculo de verificación único para [comprobar la página educativa de LinkedIn](#verify-the-linkedin-school-page) y asociarla con el Entrenador profesional.

10. Para confirmar que la verificación y la configuración se enviaron correctamente, compruebe que el [estado de la configuración del Entrenador profesional](#configuration-status) está marcado como **Completado**.

##### <a name="verify-the-linkedin-school-page"></a>Comprobar la página de LinkedIn School

La verificación de la página educativa de LinkedIn la debe completar el [superadministrador de la página de](https://www.linkedin.com/help/linkedin/answer/a541981) la escuela de LinkedIn de su institución educativa.

Puede comprobar los roles de administrador de su cuenta de LinkedIn iniciando sesión en LinkedIn y visitando la página de linkedin school de su institución educativa. Si su cuenta tiene asignado un rol de superadministrador, verá la **vista Superadministrador** junto al nombre de su institución educativa en la página de LinkedIn. Si no ve la etiqueta **Vista superadministrador** , entonces no es superadministrador de la página de su escuela.

1. Después de que el administrador de Teams envíe la **dirección URL de la página educativa de LinkedIn** , la página mostrará el **vínculo de verificación** y la **expiración del vínculo de verificación**. El vínculo de verificación expira después de 30 días.

   ![Screnshot que muestra las conexiones de LinkedIn para la aplicación entrenador profesional.](media/career-coach-linkedin-updated.png)  

2. Copie el vínculo de verificación y compártalo con su superadministrador de la página educativa de LinkedIn.

3. La página de LinkedIn Superadministrador abrirá el vínculo de verificación para asociar el Entrenador profesional con la página de su escuela. Para obtener más información, consulte [Documentación adicional sobre la verificación de la página de LinkedIn](https://www.linkedin.com/help/linkedin/answer/102672).

4. Una vez completada la verificación, el administrador de Teams puede ver si la configuración se ha enviado correctamente comprobando si el [estado de la configuración del Entrenador](#configuration-status) profesional está marcado como **Completado**.

   ![Captura de pantalla que muestra la verificación de la página de LinkedIn en el portal de desarrolladores de LinkedIn.](media/career-coach-linkedin-verification-updated.png)

#### <a name="course-catalog"></a>Catálogo de cursos

El catálogo de cursos registra los cursos y clases ofrecidos por su institución educativa.

El Entrenador profesional usa los datos del catálogo de cursos para identificar las aptitudes de un alumno a partir de su transcripción y para sugerir cursos que realizar.

> [!IMPORTANT]
> Esta es una sección obligatoria. El Entrenador profesional no se puede activar sin un catálogo de cursos.

Estos cursos se usan dentro del Entrenador profesional en dos áreas:

- Los cursos se devuelven como parte de [los recursos de aprendizaje](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_grow_real_world_skills).  

- Los cursos y los metadatos del curso, como los títulos y las descripciones del curso, se usan para ayudar a los alumnos a identificar sus aptitudes cuando [cargan una transcripción](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_Set_up_your_profile).

Para crear el catálogo de cursos, cree una lista de todos los cursos impartidos en su institución educativa y cárguela como un archivo CSV con el [formato y el esquema del documento del catálogo del curso](#course-catalog-document-format-and-schema).

Comience con el documento del catálogo  del [curso de ejemplo](https://aka.ms/career-coach/docs/it-admins/sample-catalog)para garantizar el formato correcto.También puede hacer referencia al [formato del documento del catálogo del curso y](#course-catalog-document-format-and-schema) a las secciones de esquema para obtener más información sobre los campos necesarios y recomendados.

##### <a name="add-the-course-catalog"></a>Agregar el catálogo del curso

1. Inicie sesión en el **[Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Seleccione **Aplicaciones** >  de Teams **Administrar aplicaciones** > Buscar catálogo **de cursos** **de configuración** >  **de entrenador** >  profesional.

3. Seleccione **Cargar catálogo de** cursos > Cargar cursos en formato CSV con las columnas necesarias: courseId, title y sourceLink.
    1. Cada fila debe incluir datos para cada una de las columnas necesarias.
    1. *Incluir los campos recomendados mejora la experiencia de los alumnos al devolver mejores resultados de búsqueda e identificación de aptitudes.*

4. Para su referencia, aparecerá una vista previa de una sección del catálogo de cursos cargado.

5. Selecciona **Enviar** cuando estés listo.

6. El [estado del documento cargado](#course-catalog-status) se muestra en la página de configuración.

7. Para confirmar que la configuración se ha enviado correctamente, compruebe que el [estado de la configuración del Entrenador profesional](#configuration-status) está marcado como **Completado**.

Para cargar un nuevo archivo, asegúrese de que el último archivo está desactivado seleccionando (X) para cerrar la vista previa del documento. Esta acción permitirá que el botón **Cargar** se vuelva a mostrar.

![Captura de pantalla que muestra la sección del catálogo del curso de la aplicación entrenador profesional.](media/course-catalog-updated.png)

##### <a name="course-catalog-document-format-and-schema"></a>Formato y esquema del documento del catálogo de cursos

El documento debe estar en formato CSV con un tamaño máximo de 18 MB. Los archivos de gran tamaño deben dividirse en varios archivos más pequeños que incluyan un máximo de 15.000 filas para que el procesamiento sea correcto.

El documento debe contener los metadatos del curso necesarios: **título del curso**,  **id**. del curso y  **dirección URL del curso**.

Comience con el documento del [catálogo del curso de ejemplo]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) para garantizar el formato correcto. *Incluir los campos recomendados mejora la experiencia de los alumnos al devolver mejores resultados de búsqueda e identificación de aptitudes.*

En la tabla siguiente se muestran los elementos que se incluirán en el catálogo del curso.

| Nombre             | Estado      | Tipo   | Descripción                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| CourseId         | Obligatorio    | Cadena | El courseId se asigna a lo que se genera en la transcripción del alumno.             |
| Título            | Obligatorio    | Cadena | Título del curso.                                                              |
| sourceLink       | Obligatorio    | Dirección URL    | Vínculo al sitio web a la página del curso para obtener más información sobre el curso y el plan de estudios.   |
| Descripción      | Recomendado | Cadena | Texto de introducción del curso que describe los objetivos de aprendizaje.       |
| language         | Recomendado | Cadena | Idioma del curso. Use códigos de idioma estándar.                           |
| Formato           | Recomendado | Cadena | Modo de enseñanza (en línea, vídeo, en persona).                                   |
| miniaturaLink    | Recomendado | Dirección URL    | Vínculo en miniatura a la imagen del curso.                                            |
| miniaturaAltTexto | Recomendado | Cadena | Texto alternativo de accesibilidad para la imagen                                           |
| nivel educativo   | Recomendado | Cadena | Nivel de estudio, por ejemplo. Pregrado/Graduado.                                       |
| Temas           | Recomendado | Cadena | Temas o etiquetas que están asociados con las habilidades que los cursos enseñan.          |

##### <a name="course-catalog-status"></a>Estado del catálogo de cursos

El estado del catálogo del curso se muestra en la página Configuración del catálogo del curso una vez que se ha cargado un documento, proporcionando detalles del estado de carga y procesamiento del documento.

Durante el procesamiento, el Entrenador profesional analizará el documento en busca de duplicados, normalizará y enriquecerá el catálogo mediante la extracción de aptitudes de títulos y descripciones, y lo almacenará para su uso en la página Aprender y durante las cargas de transcripción de los alumnos para su identificación de aptitudes.

![Captura de pantalla que muestra el estado de carga del catálogo del curso de la aplicación entrenador profesional.](media/career-coach-course-catalog-status-updated.png)

| Columna           | Valor     | Descripción                                                                                        |
| ---------------- | --------- | -------------------------------------------------------------------------------------------------- |
| Tiempo cargado    | Timestamp | Fecha y hora en que un administrador de TI cargó un documento.                                                     |
| Tiempo completado   | Timestamp | Fecha y hora en que el documento se procesó por completo.                                               |
| Cursos cargados | Entero   | Número de cursos encontrados en el documento.                                                           |
| Estado de ingestión | Pending   | Documento en cola para su procesamiento.                                                                  |
| Estado de ingestión | Corriendo   | El documento se está procesando actualmente. Este proceso puede tardar hasta 6 horas en función del tamaño del documento. |
| Estado de ingestión | Correcto   | Se ha completado el proceso de ingestión y los cursos estarán disponibles en el Entrenador profesional una vez que se hayan configurado todas las opciones necesarias. |
| Estado de ingestión | Fallado    | Comprueba el formato del documento y vuelve a cargarlo.                                                           |
| Duplicados       | Entero   | Número de cursos duplicados que se encuentran en el documento.                                                 |

Si una columna del estado del catálogo del curso está en blanco, el documento se está procesando y esos valores no están disponibles. Este proceso puede tardar hasta 6 horas en función del tamaño del catálogo. Una vez procesado el documento, los valores se rellenarán. Puedes actualizar la página para buscar actualizaciones.

#### <a name="fields-of-study"></a>Campos de estudio

Los campos de estudio son sinónimos de las principales áreas de interés, asignaturas principales y programas de grado. Estos campos de estudio son referenciados por los estudiantes cuando empiezan a usar el Entrenador profesional y comienzan a configurar su perfil personalizado.

La lista de campos permite a los estudiantes descubrir campos de estudio que puedan interesarles y agregar su enfoque académico planeado a su perfil en Entrenador profesional.

> [!IMPORTANT]
> Esta es una sección obligatoria. El Entrenador profesional no se puede activar sin una lista de campos de estudio.
>
> Agregue todos los campos de estudio disponibles para los alumnos, como Ingeniería, Inglés, Empresa, etc.

##### <a name="add-the-fields-of-study"></a>Agregar los campos de estudio

1. Inicie sesión en el **[Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Seleccione **Aplicaciones** >  de Teams **Administrar aplicaciones** > Buscar **campos de estudio de** **configuración** >   del **entrenador** >  profesional.

3. Seleccione **Cargar** para cargar los campos del archivo de estudio en formato CSV. Aparecerá una vista previa de los campos del documento de estudio.

4. Selecciona **Enviar**.

5. Para confirmar que la configuración se ha enviado correctamente, compruebe que el [estado de la configuración del Entrenador profesional](#configuration-status) está marcado como **Completado**.

##### <a name="fields-of-study-document-format-and-schema"></a>Campos del formato y esquema del documento de estudio

El documento debe estar en formato CSV con un tamaño máximo de 18 MB. El documento debe contener los metadatos necesarios: **Nombre del campo del estudio**.

La tabla siguiente muestra los elementos que se incluirán en los campos de estudio:

| Nombre          | Estado   | Tipo   | Descripción                    |
|---------------|----------|--------|--------------------------------|
| camposOfStudy | Obligatorio | Cadena | El nombre del campo de estudio |

#### <a name="customization-options"></a>Opciones de personalización

La configuración de personalización permite agregar oportunidades para obtener experiencias del mundo real en el panel que su institución educativa ofrece a los alumnos.

Los vínculos recomendados deben ayudar a los estudiantes a obtener experiencia real, como paneles de trabajo, eventos, oficina de servicios profesionales, eventos relacionados con la carrera y clubes estudiantiles.

1. Inicie sesión en el **[Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Seleccione **Aplicaciones** >  de Teams **Administrar aplicaciones** > Buscar configuración **del entrenador** > **profesional**.

3. Selecciona **Personalizar la experiencia** >  **+ Agregar**

4. Agrega cada **título**, **dirección URL** y **descripción de información** > Selecciona **Aplicar**.

5. Aparecerá una vista previa de la información agregada.

6. Selecciona **Enviar**.

### <a name="career-coach-settings-status"></a>Estado de la configuración de Entrenador profesional

La página configuración de Entrenador profesional del Centro de administración de Teams proporciona un resumen de estado de los pasos incompletos, pendientes, completados y fallidos para configurar el Entrenador profesional.

El mensaje de estado puede ayudarle a determinar si el Entrenador profesional está correctamente configurado y listo para su publicación para su inquilino.

#### <a name="configuration-status"></a>Estado de configuración

La sección de estado de configuración de la página de configuración de la aplicación mostrará el estado en tiempo real con la siguiente leyenda.

![Captura de pantalla que muestra la sección de estado de configuración de la aplicación entrenador profesional.](media/career-coach-config-status-updated.png)

| Categoría                    | Estado                                        | Descripción                                                 |
| --------------------------- | --------------------------------------------- | ----------------------------------------------------------- |
| Estado del aprovisionamiento del servicio | El Entrenador profesional está inicializando su inquilino.     | El aprovisionamiento del servicio se realiza automáticamente al acceder a la página de configuración de Entrenador profesional. Los cambios de configuración no se aceptarán hasta que se complete la configuración inicial. El tiempo estimado para el aprovisionamiento del servicio es de hasta 15 minutos. |
| Estado del aprovisionamiento del servicio | El Entrenador profesional está listo para configurarse.       | La página de configuración del Entrenador profesional está lista para que el administrador de TI envíe la configuración. |
| Marca y preferencias       | No iniciado                                   | Es necesario enviar la configuración. |
| Marca y preferencias       | Falta: icono aprendizaje                        | Cargue la imagen en miniatura del contenido de aprendizaje que falta. |
| Marca y preferencias       | Falta: logotipo                                 | Cargue el icono de institución que falta. |
| Marca y preferencias       | Falta: nombre de la institución                     | Cargue el nombre de la institución que falta. |
| Marca y preferencias       | Íntegro                                      | No es necesario realizar ninguna acción adicional. La configuración está completa. |
| Carga del catálogo de cursos       | No iniciado                                   | El CSV del catálogo de cursos debe enviarse. |
| Carga del catálogo de cursos       | Falta: carga correcta del catálogo del curso   | Compruebe el estado del catálogo del curso para obtener más información sobre el procesamiento del catálogo del curso. |
| Carga del catálogo de cursos       | Íntegro                                      | No es necesario realizar ninguna acción adicional. La configuración está completa. |
| Conexión educativa de LinkedIn  | No iniciado                                   | Es necesario enviar la dirección URL de la página educativa de LinkedIn. |
| Conexión educativa de LinkedIn  | Falta: dirección URL de una página educativa de LinkedIn aprobada | Esperando la aprobación de la comprobación del superadministrador de la página de LinkedIn School. |
| Conexión educativa de LinkedIn  | Íntegro                                      | No es necesario realizar ninguna acción adicional. La configuración está completa. |
| Campos de carga del estudio      | No iniciado                                   | El csv de campo de estudio debe enviarse. |
| Campos de carga del estudio      | Falta: áreas de interés                    | Compruebe si el campo de carga del estudio es correcto. |
| Campos de carga del estudio      | Íntegro                                      | No es necesario realizar ninguna acción adicional. La configuración está completa. |

Una vez que todos los pasos necesarios se marquen como completados, el Entrenador profesional se puede liberar correctamente a su inquilino.

## <a name="step-5-make-career-coach-available-to-your-institution"></a>Paso 5: Hacer que el Entrenador profesional esté disponible para su institución

En este punto, se ha configurado el Entrenador profesional para su institución.

A continuación, siga estos pasos para asegurarse de que el Entrenador profesional esté disponible para su institución en Microsoft Teams.

### <a name="assign-career-coach-licenses-to-users"></a>Asignar licencias de Entrenador profesional a usuarios

Para obtener instrucciones detalladas, consulte [Asignar licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="set-up-policies-and-pin-the-app"></a>Configurar directivas y anclar la aplicación

Anclar entrenador profesional lo agregará a la barra izquierda de la ventana de Microsoft Teams para que sea más accesible y visible para los alumnos. Si prefiere anclar entrenador profesional para un subconjunto de los usuarios, tendrá que implementar una [directiva de configuración](teams-app-setup-policies.md) con ese grupo incluido.

1. Inicie sesión en el **[Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Seleccione **Directivas****de configuración de** aplicaciones  >  de Teams y seleccione la directiva que prefiera.

    Si no está seguro de qué directiva usar, consulte la documentación de administración de directivas de [Microsoft Teams](policy-packages-edu.md) o use el Asistente para directivas de [educación](easy-policy-setup-edu.md) para configurar una directiva para Microsoft Teams.

3. En **Aplicaciones ancladas**, elige **Agregar aplicaciones**.

4. Selecciona la directiva que prefieras en **Buscar en función de esta directiva de permisos de aplicación**.

5. Busque **Entrenador profesional** en **Buscar por nombre** y, a continuación, seleccione  **Agregar** > **Agregar** para cerrar el panel.

6. Elige el orden en que aparecerá la aplicación y selecciona **Confirmar**.

Los alumnos recibirán una notificación en Microsoft Teams de que se ha anclado el Entrenador profesional.
