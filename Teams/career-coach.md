---
title: Compre, configure y habilite El entrenador profesional para Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo comprar, configurar y habilitar El entrenador profesional para Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ec7ef2f09728abdb2db8acc3be948a50faaf304
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684577"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>Compre, configure y habilite El entrenador profesional para Microsoft Teams

Entrenador profesional es una aplicación Microsoft Teams para el sector educativo con tecnología de LinkedIn que proporciona orientación personalizada para que los estudiantes de educación superior puedan navegar por su trayectoria profesional. Career Coach ofrece a las instituciones educativas una solución profesional unificada para que los alumnos descubran su trayectoria profesional, aumenten las aptitudes del mundo real y construyan su red en un solo lugar.

Más información sobre [El entrenador profesional.](https://aka.ms/career-coach)

> [!NOTE]
> Use los procedimientos recomendados y sugerencias útiles de esta guía para habilitar las capacidades del Entrenador profesional para estudiantes, profesores y personal. Vea el [artículo Guía de planeación](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) rápida.

## <a name="review-the-requirements"></a>Revisar los requisitos

Para habilitar Career Coach para su institución educativa, revise lo que necesita para que la aplicación esté en funcionamiento.

**Requisitos técnicos**

  - Office 365 inquilino con Azure Active Directory

  - Microsoft Teams

  - Conexiones de cuentas de LinkedIn en Azure Active Directory

**Licencias**

  - Profesores 

  - Estudiantes

> [!NOTE]
> Se debe asignar una licencia de profesor de entrenador profesional al administrador de TI que complete la configuración.

**Datos y archivos de su institución educativa**

  - Datos del catálogo de cursos

  - Campos de estudio ofrecidos

  - Página de LinkedIn de la institución educativa

  - Suscripción a un campus de LinkedIn Learning (preferido)

## <a name="purchase-the-career-coach-licenses"></a>Comprar las licencias de Entrenador profesional

Career Coach está disponible en todo el mundo (excepto China y Rusia) para instituciones de educación superior calificadas a través de Enrollment for Education Solutions (EES), Proveedores de servicios en la nube (CSP) y Microsoft 365 centro de administración (web direct). Como aplicación Microsoft Teams, los clientes deben tener Microsoft 365 A3/A5 o Office 365 A1/A3/A5.

### <a name="assign-app-licenses-to-users"></a>Asignar licencias de aplicaciones a usuarios

Para obtener instrucciones paso a paso, vea [Asignar licencias a usuarios.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="turn-on-linkedin-account-connections"></a>Activar las conexiones de cuentas de LinkedIn

El Entrenador **profesional requiere** que los usuarios de su institución educativa tengan la capacidad de conectar su cuenta de Microsoft 365 a su cuenta de LinkedIn que se facilita en El entrenador profesional

1. Inicie sesión en el [Centro de administración de Azure AD](https://aad.portal.azure.com/) con una cuenta que sea administrador global de la organización de Azure AD.

2. Seleccione **Usuarios**.

3. En la **página Usuarios,** seleccione **Configuración de usuario.**

4. En **Conexiones de cuentas de LinkedIn,** permite a los usuarios conectar sus cuentas para acceder a sus conexiones de LinkedIn dentro de algunas aplicaciones de Microsoft. No se comparte ningún dato hasta que los usuarios consienten conectar sus cuentas.

   - Seleccione **Sí** para habilitar el servicio para todos los usuarios de su institución educativa

   - Seleccione **Grupo seleccionado para** habilitar el servicio solo para un grupo de usuarios seleccionados en su institución educativa

   - Seleccione **No** para retirar el consentimiento de todos los usuarios de su institución educativa

Obtenga información sobre cómo [integrar conexiones de cuenta de LinkedIn en Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="configure-career-coach-in-the-teams-admin-center"></a>Configurar El entrenador profesional en el centro Teams administración

Con la configuración de administrador del centro Microsoft Teams administración, puede configurar El entrenador profesional para su institución educativa y habilitarlo para los usuarios.

## <a name="access-the-career-coach-app-settings"></a>Acceder a la configuración de la aplicación Entrenador profesional

Use la [página Administrar aplicaciones](/microsoftteams/manage-apps) para ver Teams aplicaciones en el catálogo de aplicaciones de su institución educativa.

1. Inicie sesión en el **Teams de administración**.

2. En el panel de navegación izquierdo, **selecciona Teams aplicaciones Administrar**  >  **aplicaciones.**  

    > [!NOTE]
    > Debe ser administrador global o administrador Teams de servicio para acceder a la página.

3. Busque o busque Entrenador **profesional.**  

4. Seleccione **Entrenador profesional** y, a continuación, seleccione **Configuración.**  

    ![muestra la aplicación Entrenador profesional seleccionada con la Configuración que se muestra](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a>Configurar la configuración de la aplicación Entrenador profesional

Entrenador profesional tiene cinco categorías de configuración:

- [Marca y preferencias](#brand-and-preferences)

- [Configuración de LinkedIn](#linkedin-configuration)

- [Catálogo de cursos](#course-catalog)

- [Campos de estudio](#fields-of-study)

- [Personalización](#customization)

> [!NOTE]
> La marca y las preferencias, la configuración  de LinkedIn, el catálogo de cursos y los campos de estudio son necesarios para habilitar de forma eficaz la aplicación para estudiantes, profesores y personal.

#### <a name="brand-and-preferences"></a>Marca y preferencias

Establezca el nombre, el logotipo y el idioma predeterminado de la institución educativa en la página de configuración de marca y preferencias.

![la sección de personal de marca de Coach profesional del Centro de administración](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a>Icono de institución educativa

El icono de institución educativa se usa en todo el Coach profesional para identificar contenido exclusivo de su institución educativa, recursos del catálogo de cursos en toda la aplicación y en la sección de experiencias del mundo real del panel. El icono tiene el formato más adecuado:

 - Un PNG transparente
 - Relación de aspecto de 1:1
 - Tamaño máximo de 64 px x 64 px.

##### <a name="educational-institution-thumbnail"></a>Miniatura de institución educativa

El icono de institución educativa se usará para los recursos del catálogo del curso en toda la aplicación cuando una imagen específica no esté disponible para un curso. El icono tiene el formato más adecuado:

- UN PNG
- Relación de aspecto de 16:9
- Tamaño máximo de 360 px x 200 px.

#### <a name="linkedin-configuration"></a>Configuración de LinkedIn

La configuración de LinkedIn conecta el Coach profesional con datos de antiguos alumnos públicos de LinkedIn.

> [!NOTE]
> El Entrenador profesional no se puede habilitar sin la conexión de página de LinkedIn verificada.

##### <a name="add-and-confirm-the-linkedin-page"></a>Agregar y confirmar la página de LinkedIn

Determine la página de LinkedIn de la institución educativa. Busque la página de LinkedIn buscando en LinkedIn o conectándose con un miembro del personal de los servicios profesionales para determinar la página correcta para usar.  
  
1. Inicie sesión en el **Teams de administración**.

1. Selecciona **Teams aplicaciones Administrar**  >  **aplicaciones** Profesional  >  **Coach** Conexión de  >  **LinkedIn**.

2. Escriba la dirección URL de la página de LinkedIn de su institución educativa.  

3. Seleccione **Aplicar**.

4. Copie la dirección URL de verificación y compártella con la documentación de administrador de página de LinkedIn del administrador de la página de [LinkedIn de su](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en)institución educativa. El vínculo de verificación expira después de 30 días.  

   ![configuración de linkedin para el entrenador profesional](media/linkedin.png)  

#### <a name="course-catalog"></a>Catálogo de cursos

El catálogo de cursos representa los cursos y clases ofrecidos a los alumnos por su institución educativa. Estos cursos se usan dentro de la aplicación en dos áreas:

- Los cursos se devuelven como parte de los recursos de aprendizaje.  

- Los metadatos de cursos y cursos, como las descripciones, se usan para ayudar a los alumnos a identificar sus aptitudes al cargar una transcripción.  

Para crear el catálogo de cursos, cree una lista de todos los cursos que se imparten en su institución educativa y cargúenlo como un archivo CSV. La aplicación se basa en el catálogo de cursos para identificar las aptitudes de un alumno de su transcripción y sugerir cursos para realizar. 

> [!NOTE]
> Vea [Ubicación de datos en Teams](location-of-data-in-teams.md) seguridad y [cumplimiento](security-compliance-overview.md) para obtener información sobre la protección de la información de los alumnos. 

##### <a name="course-catalog-documents-formatting-and-schema"></a>Formato y esquema de documentos del catálogo de cursos

El documento debe estar en formato CSV con un tamaño máximo de 18 MB. El documento debe contener el título del curso de campos **obligatorios,** **el id. del** curso y la dirección URL del **curso.** Incluir los campos recomendados mejora la experiencia de los alumnos al devolver mejores resultados de búsqueda e identificación de aptitudes.

> [!NOTE]
> Empiece con el documento [del catálogo de cursos]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) de ejemplo para empezar.

En la tabla siguiente se muestran los elementos que se incluirán en el catálogo de cursos:


| Nombre             | Estado      | Tipo   | Descripción                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | Obligatorio    | cadena | Normalmente, el id. del curso (normalmente se asigna a lo que se genera en la transcripción). |
| título            | Obligatorio    | cadena | Normalmente, el título del curso.                                                      |
| sourceLink       | Obligatorio    | Dirección URL    | Vínculo del sitio web a la página del curso.                                               |
| descripción      | Recomendado | cadena | Texto de introducción para el curso.                                              |
| idioma         | Recomendado | cadena | Idioma del curso. Use códigos de idioma estándar.                           |
| formato           | Recomendado | cadena | Modo de enseñanza, por ejemplo, en línea, vídeo, en persona.                              |
| thumbnailLink    | Recomendado | Dirección URL    | Vínculo de miniaturas a la imagen del curso.                                            |
| thumbnailAltText | Recomendado | cadena | Texto alternativo de accesibilidad para la imagen                                           |
| educationLevel   | Recomendado | cadena | Nivel de estudio, por ejemplo. Graduación/graduación.                                       |
| temas           | Recomendado | cadena | Temas o etiquetas que están asociadas a las aptitudes que imparten los cursos.          |

##### <a name="add-the-course-catalog"></a>Agregar el catálogo de cursos

1. Inicie sesión en el **Teams de administración**.

1. Selecciona **Teams aplicaciones Administrar** &gt; **aplicaciones** &gt; **Entrenador** profesional &gt; **Configuración** catálogo del &gt; **curso.**  

2. Upload cursos en formato CSV.

4. Seleccione **Aplicar**.

   ![la sección catálogo de cursos de la aplicación de entrenador profesional](media/course-catalog.png)

#### <a name="fields-of-study"></a>Campos de estudio

Los campos de estudio son sinónimos de áreas principales de interés, grado académico y grado. Los alumnos hacen referencia a estos títulos cuando empiezan a usar la aplicación y empiezan a configurar su perfil personalizado.

Agregue todos los campos de estudio disponibles para los alumnos, como Ingeniería, Inglés, Empresa, entre otros. La lista de campos permite a los alumnos descubrir campos de estudio que puedan interesarlos y agregar su área de enfoque a su perfil.

> [!NOTE]
> Empiece con el [campo de ejemplo del documento de](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) estudio.
##### <a name="add-the-fields-of-study"></a>Agregar los campos de estudio

1. Inicie sesión en el **Teams de administración**.
1. Selecciona **Teams aplicaciones Administrar** &gt; **aplicaciones** &gt; **Entrenador** profesional &gt; **Configuración** campos de &gt; **estudio.**  

2. Upload campo de estudio en formato CSV.

3. Seleccione **Aplicar**.

#### <a name="customization"></a>Personalización

El Entrenador profesional se puede personalizar para que sea único para su institución educativa. La personalización permite agregar experiencias al panel. Se recomienda agregar vínculos a paneles de trabajo, eventos, oficina de servicios profesionales, eventos profesionales, clubes de estudiantes y cualquier otro recurso que ayude a los estudiantes a obtener experiencia en el mundo real.

##### <a name="add-customized-experiences"></a>Agregar experiencias personalizadas

1. Inicie sesión en el **Teams de administración**.

1. Selecciona **Teams aplicaciones Administrar** &gt; **aplicaciones** Career &gt; **Coach**  >  **Configuración** &gt; **Personalización.**

2. Agregue cada dirección URL, un título y una descripción breve.  
  
3. Seleccione **Aplicar**.

## <a name="making-career-coach-available-to-your-organization"></a>Hacer que El entrenador profesional esté disponible para su organización

Ahora que el Coach profesional se ha configurado para su organización. Siga estos pasos para asegurarse de que el Entrenador profesional está disponible para la organización en Microsoft Teams.

### <a name="enable-the-app"></a>Habilitar la aplicación

Después de completar la configuración, habilite la aplicación para estudiantes y usuarios con licencia para que tengan acceso a Entrenador profesional.  
  
> [!NOTE]
> Debe tener permisos de rol de administrador Teams global o de administrador.

1. Inicie sesión en el **Teams de administración**.

1. Selecciona **Teams aplicaciones Administrar** &gt; **aplicaciones** Entrenador &gt; **profesional.**

2. Mueva el botón de alternancia Estado a **Permitido.**  

  > [!NOTE]
  > Permitido significa que la aplicación está disponible para los usuarios de su institución educativa. Bloqueado significa que la aplicación no está disponible para los alumnos.

### <a name="add-career-coach-as-an-installed-app"></a>Agregar Entrenador profesional como una aplicación instalada

> [!NOTE]
> En este paso se asegura 1) de que el Entrenador profesional esté configurado correctamente para su organización 2) que los alumnos encuentren Coach profesional.

1. Inicie sesión en el **Teams de administración**.

2. Seleccione **Teams directivas de configuración** de &gt; **aplicaciones** Su &gt; *directiva*. 

3. En Aplicaciones instaladas, seleccione Agregar aplicaciones.

4. En el panel Agregar aplicaciones instaladas, busque las aplicaciones que desea instalar automáticamente para los usuarios cuando inicien Teams. También puede filtrar aplicaciones por directiva de permisos de aplicación. Cuando haya elegido la lista de aplicaciones, seleccione Agregar.

### <a name="pin-the-app"></a>Anclar la aplicación

Anclar El entrenador profesional hará que la aplicación sea más accesible y visible para los alumnos.

1. Inicie sesión en el **Teams de administración**.

2. Seleccione **Teams directivas de configuración** de &gt; **aplicaciones** Su &gt; *directiva*. 

3. En **Aplicaciones ancladas,** elija **Agregar aplicaciones.**

4. Busque Entrenador **profesional** y, a continuación, **seleccione Agregar**.

5. Elija el orden para que aparezca la aplicación y seleccione **Guardar.**

> [!NOTE]
> Los alumnos recibirán una notificación en Microsoft Teams que el Entrenador profesional se ha anclado.

Para [obtener más información,](/microsoftteams/teams-app-setup-policies) haga referencia a Administrar directivas de configuración de aplicaciones en Microsoft.

## <a name="resources"></a>Recursos

Los siguientes recursos le ayudarán a planear la aplicación Entrenador profesional.

- [Bienvenido a Microsoft Teams](Teams-overview.md)

- [Cómo implementar Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Información general de los equipos y canales en Microsoft Teams](teams-channels-overview.md)

- [Administrar aplicaciones en el Microsoft Teams de administración](manage-apps.md)

- [Seguridad, privacidad y cumplimiento en Microsoft Teams](security-compliance-overview.md)

- [Kit de orientación virtual en línea](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [Límites y especificación de Teams canales](limits-specifications-teams.md)

- [Ubicación de los datos en Microsoft Teams](location-of-data-in-teams.md)

- [Introducción a la formación de administradores para Microsoft Teams](ITAdmin-readiness.md)

- [Solución de problemas de Teams](/microsoftteams/troubleshoot/teams-welcome)

- [Administrar directivas de permisos de aplicación en Microsoft Teams](teams-app-permission-policies.md)
