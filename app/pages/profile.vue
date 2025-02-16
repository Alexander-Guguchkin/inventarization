<template>
    <div class="profile">
        <PageWrapper>
            <div class="profile__wrapper">
                <div class="profile__header">
                    <div class="user">
                        <div class="avatar">
                            <UAvatar src="https://github.com/benjamincanac.png" size="3xl" />
                            <div class="username">ФИО: TestUser</div>
                        </div>
                        <div class="position">Должность: Системный администратор</div>
                        <div class="status">
                            Статус: <UBadge color="primary" variant="subtle">Работает</UBadge>
                        </div>
                        <!-- // работает или в отпуске -->
                    </div>
                    <div class="buttons">
                        <div class="edit">
                            <UButton icon="lucide:user-round-pen" />
                        </div>
                        <div class="logout">
                            <UButton icon="lucide:log-out" />
                        </div>
                    </div>
                </div>
                <div class="profile__main">
                    <div class="contacts">
                        <div class="phone-number">Номер телефона: +7-xxx-xxx-xxx</div>
                        <div class="email">Почта: test@example.com</div>
                        <div class="messenger"></div>
                        <!-- сделать кнопки которые будут переносить на общение в соц сети с данным пользователем -->
                    </div>
                    <div class="additional__information">
                        <div class="date-born">Дата рождения: xx-xx-xxxx</div>
                        <div class="role">Роль: администратор</div>
                        <!-- администратор или обычный пользователь -->
                        <div class="departments">Отдел: testDep</div>
                        <!-- отдел или команда -->
                    </div>
                    <div class="profile__statistics">
                        <div class="task-success">Выполненные задачи: task 1</div>
                    </div>
                </div>
                <div class="profile__tasks">
                    <div class="main-tasks">
                        Текущие задачи: task 0
                    </div>
                    <div class="history-tasks">
                        История задач: task
                    </div>
                </div>
                <div class="profile__responsibilities">
                    Обязанности: 1с, сервера, active directory
                </div>
            </div>
        </PageWrapper>
    </div>
</template>
<style scoped>
.profile__header {
    display: grid;
    grid-template-columns: 1fr 1fr;
}

.user,
.buttons {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.buttons {
    justify-self: end;
}

.user-info {
    font-weight: bold;
    font-size: 36px;
}
</style>