code ~/.bashrc   ----- Запускает внутренний файл вс код -----

export VIRTUAL_ENV_DISABLE_PROMPT=1

# 2. Функция для чистого вывода venv (без лишних символов)
get_venv() {
    if [ -n "$VIRTUAL_ENV" ]; then
        # Желтый цвет для имени окружения
        echo -ne "\[\033[33m\]($(basename "$VIRTUAL_ENV")) \[\033[0m\]"
    fi
}

# 3. Алиасы с правильным экранированием цветов
alias zen='export PS1="$(get_venv)\[\033[01;32m\]>> \[\033[00m\]"'
alias info='export PS1="$(get_venv)\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[36m\]\$(__git_ps1 \" (%s)\")\[\033[00m\]\$ "'
