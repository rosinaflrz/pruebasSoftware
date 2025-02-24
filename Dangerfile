# Dangerfile

# Obtiene el mensaje del último commit
commit_message = git.commits.last.message

# Reglas de validación
fail("El título del commit no debe superar los 50 caracteres.") if commit_message.split("\n").first.length > 50
fail("Debe haber una línea en blanco entre el título y la descripción.") if commit_message.lines[1]&.strip != ""
fail("La descripción debe tener al menos 5 caracteres.") if commit_message.lines[2..]&.join&.strip.to_s.length < 5
fail("Cada línea de la descripción no debe superar los 72 caracteres.") if commit_message.lines[2..]&.any? { |line| line.strip.length > 72 }
