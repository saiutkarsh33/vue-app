<template>
    <div>

        <div class="label-title">Personal Details</div>
        <div class="input-content">
            <div>
                <sgds-input label="First Name"  placeholder="First Name" />
            </div>
            <div>
                <sgds-input label="Last Name" placeholder="Last Name" />
            </div>
            <div>
                <sgds-radio-group label = "Gender">
                    <sgds-radio value="male">Male</sgds-radio>
                    <sgds-radio value="female">Female</sgds-radio>
                </sgds-radio-group>
            </div>

        </div>

    </div>
</template>

<style>
.input-content {
    display: flex;
    flex-direction: column;
    gap: 15px;
}

.label-title {
    font-family: var(--sgds-font-family-brand);
    font-size: var(--sgds-font-size-4);
    font-weight: var(--sgds-font-weight-bold);
    padding-bottom: var(--sgds-padding-lg);
}

</style>