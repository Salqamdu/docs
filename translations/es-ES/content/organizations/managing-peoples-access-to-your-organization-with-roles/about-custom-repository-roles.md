---
title: Acerca de los roles de repositorio personalizados
intro: Puedes controlar el acceso a los repositorios de tu organización de forma más granular con roles de repositorio personalizados.
versions:
  feature: custom-repository-roles
topics:
  - Organizations
  - Teams
shortTitle: About custom roles
ms.openlocfilehash: 48c6fe2ee78d2d28d11093d0b50a472c46266959
ms.sourcegitcommit: ca040a1871ab5e929b596686ef955b02c5afa051
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: '148131028'
---
{% data reusables.organizations.custom-repo-roles-ghec-only %}

## Acerca de los roles de repositorio personalizados

Para llevar a cabo cualquier acción en {% data variables.product.product_name %}, tal como crear una solicitud de cambios en un repositorio o cambiar los ajustes de facturación de una organización, los individuos deben tener acceso suficiente a la cuenta o recurso relevante. Los permisos son los que controlan este tipo de acceso. Un permiso es la capacidad de llevar a cabo una acción específica. Por ejemplo, la capacidad de borrar una propuesta constituye un permiso. Un rol es un conjunto de permisos que puedes asignar a los individuos o equipos.

Dentro de una organización, puedes asignar roles a nivel de repositorio, equipo u organización. Para obtener más información acerca de los distintos niveles de roles, vea "[Roles en una organización](/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization)".

Puede tener un control más pormenorizado sobre los permisos que concede en el nivel de repositorio. Para ello, cree hasta tres roles de repositorio personalizados. {% data reusables.organizations.about-custom-repo-roles %} Para obtener más información, consulte "[Administración de roles de repositorio personalizados para una organización](/organizations/managing-peoples-access-to-your-organization-with-roles/managing-custom-repository-roles-for-an-organization)".

Después de que creas un rol personalizado, cualquiera con acceso administrativo a un repositorio puede asignar el rol a un individuo o equipo. Para obtener más información, consulta "[Administración del acceso de una persona a un repositorio de la organización](/organizations/managing-access-to-your-organizations-repositories/managing-an-individuals-access-to-an-organization-repository)" y "[Administración del acceso de equipo a un repositorio de la organización](/organizations/managing-access-to-your-organizations-repositories/managing-team-access-to-an-organization-repository)".

{% ifversion custom-repo-role-api %}

También puedes usar la API de REST para crear y administrar roles de repositorio personalizados. Para obtener más información, consulta "[Roles de repositorio personalizados](/rest/orgs/custom-roles)".

{% else %}

También puedes usar la API de REST para enumerar los roles de repositorio personalizados disponibles en tu organización. Para obtener más información, consulta "[API de roles de repositorio personalizados](/rest/orgs/custom-roles)".

{% endif %}

## Acerca del rol heredado

Cuando creas un rol de repositorio personalizado, comenzarás eligiendo un rol heredado de un conjunto de opciones predefinidas. El rol heredado determinará el conjunto inicial de permisos que se incluyen en el rol personalizado. Entonces, podrás seguir personalizando el rol si eliges permisos adicionales para asignarle a este. Para obtener la lista completa de permisos disponibles, vea "[Permisos adicionales para roles personalizados](#additional-permissions-for-custom-roles)".

Tus opciones para escoger el rol heredado se estandarizan para tipos diferentes de contribuyentes en tu repositorio.

| Rol heredado | Diseñada para |
|----|----|
| **Lectura** | Contribuyentes sin código que quieren ver o debatir en tu proyecto |
| **Evaluación de errores** | Contribuyentes que necesitan administrar propuestas y solicitudes de cambio proactivamente sin acceso de escritura |
| **Escritura** | Miembros de la organización y colaboradores que suben información a tu proyecto activamente |
| **Mantenimiento** | Administradores de proyectos que necesitan administrar el repositorio sin acceso a las acciones destructivas o sensibles |

## Roles personalizados de ejemplo

Aquí te mostramos ejemplos de los roles de repositorio personalizados que puedes configurar.

| Rol de repositorio personalizado | Resumen | Rol heredado | Permisos adicionales |
|----|----|----|----|
| Ingeniero de seguridad | Puede contribuir con código y mantener el mapa de seguridad | **Mantenimiento** | Borrar los resultados del escaneo de código |
| Contractor | Puede desarrollar integraciones de webhooks | **Escritura** | Administrar webhooks |
| Adminsitrador de comunidad | Puede manejar todas las interacciones de la comunidad sin poder contribuir con código | **Lectura** | - Marcar una incidencia como duplicada <br> - Administrar la configuración de la página de GitHub <br> - Administrar la configuración de la wiki <br> - Establecer la versión preliminar social <br> - Editar metadatos del repositorio <br> - Discusiones de evaluación de prioridades |

## Permisos adicionales para los roles personalizados

Después de haber elegido un rol heredado, puedes seleccionar los permisos adicionales para tu rol personalizado.

Solo puedes elegir un permiso adicional si no se ha incluido ya en el rol heredado. Por ejemplo, si el rol heredado ofrece acceso de **Escritura** en un repositorio, el permiso de "Cerrar una solicitud de incorporación de cambios" ya se habrá incluido en el rol heredado.

{% ifversion discussions %}
### Debates

- **Crear una categoría de discusión**: capacidad para crear una nueva categoría de discusión. Para obtener más información, consulta "[Crear una nueva categoría de discusión](/discussions/managing-discussions-for-your-community/managing-categories-for-discussions#creating-a-category)".
- **Editar una categoría de discusión**: capacidad para editar una categoría de discusión. Para obtener más información, consulta «[Editar una categoría de discusión](/discussions/managing-discussions-for-your-community/managing-categories-for-discussions#editing-a-category)».
- **Eliminar una categoría de discusión**: capacidad para eliminar una categoría de discusión. Para obtener más información, consulta «[Eliminar una categoría de discusión](/discussions/managing-discussions-for-your-community/managing-categories-for-discussions#deleting-a-category)».
- **Marcar o desmarcar respuestas de discusión**: capacidad de marcar respuestas a una discusión si la categoría de la discusión acepta respuestas. Para obtener más información, consulta "[Marcar o desmarcar comentarios en una discusión como la respuesta](/discussions/managing-discussions-for-your-community/moderating-discussions#marking-a-comment-as-an-answer)".
- **Ocultar o mostrar comentarios de discusión**: capacidad de ocultar y mostrar comentarios en una discusión.  Para más información, vea "[Moderación de debates](/communities/moderating-comments-and-conversations/managing-disruptive-comments#hiding-a-comment)".
- **Convertir problemas en discusiones**: capacidad para convertir un problema en una discusión.  Para obtener más información, consulta «[Conversión de problemas en discusiones](/discussions/managing-discussions-for-your-community/moderating-discussions#converting-an-issue-to-a-discussion)».
{% endif %}

### Propuestas y solicitudes de cambios

- **Asignar o eliminar a un usuario**: asigna un usuario a una solicitud o solicitud de incorporación de cambios, o lo elimina de ellas.
- **Agregar o eliminar etiqueta**: agrega una etiqueta a una incidencia o solicitud de incorporación de cambios, o la elimina de ellas.

### Problema

- **Cerrar una incidencia**
- **Volver a abrir una incidencia que se había cerrado**
- **Eliminar una incidencia**
- **Marcar una incidencia como duplicada**

### Solicitud de incorporación de cambios

- **Cerrar una solicitud de incorporación de cambios**
- **Volver a abrir una solicitud de incorporación de cambios**
- **Solicitar una revisión de solicitud de incorporación de cambios**: solicite una revisión de un usuario o equipo.

### Repositorio

- **Establecer hitos**: agregue hitos a una incidencia o solicitud de incorporación de cambios.
- **Administrar la configuración de wiki**: active wikis para un repositorio.
- **Administrar la configuración del proyecto**: activar proyectos para un repositorio.
- **Administrar la configuración de combinación de solicitudes de incorporación de cambios**: elija el tipo de confirmaciones de combinación que se permiten en su repositorio, tales como la fusión mediante combinación, fusión mediante combinación con "squash" o fusión mediante combinación de base.
- **Administrar la configuración de {% data variables.product.prodname_pages %}** : habilite {% data variables.product.prodname_pages %} para el repositorio y seleccione la rama que quiera publicar. Para más información, vea "[Configuración de un origen de publicación para el sitio de {% data variables.product.prodname_pages %}](/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)".
- **Administrar webhooks**: agregue webhooks al repositorio.
- **Administrar claves de implementación**: agregue claves de implementación al repositorio.
- **Editar metadatos del repositorio**: actualice la descripción del repositorio, así como sus temas.
{%- ifversion ghec %}
- **Establecer límites de interacción**: restrinja temporalmente a usuarios determinados para que no puedan comentar, abrir incidencias o crear solicitudes de incorporación de cambios en el repositorio público y oblíguelos a pasar un periodo de tiempo con actividad limitada. Para más información, vea "[Limitación de las interacciones en el repositorio](/communities/moderating-comments-and-conversations/limiting-interactions-in-your-repository)".
{%- endif %}
- **Establecer la vista previa social**: agregue una imagen de identificación a su repositorio que aparezca en las plataformas de redes sociales cuando se vincule a este. Para obtener más información, vea "[Personalización de la versión preliminar de redes sociales del repositorio](/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview)".
- **Insertar confirmaciones en ramas protegidas**: inserte en una rama marcada como rama protegida. Las reglas de protección de rama se seguirán aplicando y podrían dar lugar a que se rechace una inserción.
- **Crear etiquetas protegidas**: cree etiquetas que coincidan con una regla de protección de etiquetas. Para obtener más información, vea "[Configuración de reglas de protección de etiquetas](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/configuring-tag-protection-rules)".
- **Eliminar etiquetas protegidas**: elimine etiquetas que coincidan con una regla de protección de etiquetas. Para obtener más información, consulta "[Configuración de reglas de protección de etiquetas](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/configuring-tag-protection-rules)". {% ifversion bypass-branch-protections %}
- **Omitir protecciones de rama**: realizar la inserción en una rama protegida sin necesidad de cumplir con las reglas de protección de rama. {% endif %}

### Seguridad

- **Ver los resultados de {% data variables.product.prodname_code_scanning %}** : capacidad para ver las alertas de {% data variables.product.prodname_code_scanning %}.
- **Descartar o volver a abrir los resultados de {% data variables.product.prodname_code_scanning %}** : capacidad para descartar o volver a abrir las alertas de {% data variables.product.prodname_code_scanning %}.
- **Eliminar los resultados de {% data variables.product.prodname_code_scanning %}** : capacidad para eliminar las alertas de {% data variables.product.prodname_code_scanning %}.
- **Ver {% data variables.product.prodname_dependabot_alerts %}** : capacidad para ver {% data variables.product.prodname_dependabot_alerts %}.
- **Descartar o volver a abrir {% data variables.product.prodname_dependabot_alerts %}** : capacidad para descartar o volver a abrir {% data variables.product.prodname_dependabot_alerts %}.
- **Ver los resultados de {% data variables.product.prodname_secret_scanning %}** : capacidad para ver las alertas de {% data variables.product.prodname_secret_scanning %}.
- **Descartar o volver a abrir los resultados de {% data variables.product.prodname_secret_scanning %}** : capacidad para descartar o volver a abrir las alertas de {% data variables.product.prodname_secret_scanning %}.

## Precedencia de los distintos niveles de acceso

Si se otorga a una persona los diferentes niveles de acceso mediante vías diferentes, tales como la membrecía de equipo y los permisos base de una organización, el acceso superior anulará a los otros. Por ejemplo, si un propietario de una organización otorga a los miembros organizacionales un rol personalizado que utilice el rol heredado de "Lectura" y luego el propietario configura el permiso base de la organización en "Escritura", entonces este rol personalizado tendrá el acceso de escritura en conjunto con cualquier permiso adicional que se incluya en dicho rol personalizado.

{% data reusables.organizations.mixed-roles-warning %}

Para resolver el acceso que ocasiona el conflicto, puedes ajustar los permisos básicos de tu organización o el acceso del equipo o editar el rol personalizado. Para más información, consulte:
  - "[Definición de permisos base para una organización](/github/setting-up-and-managing-organizations-and-teams/setting-base-permissions-for-an-organization)"
  - "[Administración del acceso de equipo a un repositorio de la organización](/organizations/managing-access-to-your-organizations-repositories/managing-team-access-to-an-organization-repository)"
  - "[Edición de un rol de repositorio](#editing-a-repository-role)"
