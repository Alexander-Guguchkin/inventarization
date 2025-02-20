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
                        <div class="position"><span class="name-rows">Должность</span>: Системный администратор</div>
                        <div class="status">
                            <span class="name-rows">Статус</span>: <UBadge color="primary" variant="subtle">Работает
                            </UBadge>
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
                        <div class="phone-number"><span class="name-rows">Номер телефона</span>: +7-xxx-xxx-xxx</div>
                        <div class="email"><span class="name-rows">Почта</span>: test@example.com</div>
                        <div class="messenger"></div>
                        <!-- сделать кнопки которые будут переносить на общение в соц сети с данным пользователем -->
                    </div>
                    <div class="additional__information">
                        <div class="date-born"><span class="name-rows">Дата рождения</span>: xx-xx-xxxx</div>
                        <div class="role"><span class="name-rows">Роль</span>: администратор</div>
                        <!-- администратор или обычный пользователь -->
                        <div class="departments"><span class="name-rows">Отдел</span>: testDep</div>
                        <!-- отдел или команда -->
                    </div>
                </div>
                <div class="profile__tasks">
                    <div class="main-tasks">
                        <span class="name-rows">Текущие задачи</span>: task 0
                    </div>
                    <div class="history-tasks">
                        <span class="name-rows">
                            История задач
                        </span>: task
                    </div>
                    <div class="profile__statistics">
                        <div class="task-success"><span class="name-rows">Выполненные задачи</span>: task 1</div>
                    </div>
                </div>
                <div class="profile__responsibilities">
                  <span class="name-rows">Обязанности</span>: 1с, сервера, active directory
                </div>
            </div>
        </PageWrapper>
    </div>
</template>
<style scoped>
.profile {
    font-size: 21px;
}

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

.username {
    font-weight: bold;
    font-size: 39px;
}

.avatar {
    display: flex;
    gap: 20px;
}

.profile__wrapper {
    display: grid;
    grid-template-rows: 1fr 2fr 1fr 1fr;
    gap: 15px;
}

.name-rows {
    font-weight: bold;
}
</style>