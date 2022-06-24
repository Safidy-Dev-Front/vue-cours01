<template>
    <section class="vh-100">
        <div class="container py-5 h-100">
            <div class="row d-flex justify-content-center align-items-center h-100">
                <div class="col">
                    <div class="card" id="list1" style="border-radius: .75rem; background-color: #eff1f2;">
                        <div class="card-body py-4 px-4 px-md-5">

                            <p class="h1 text-center mt-3 mb-4 pb-3 text-primary">
                                <i class="fas fa-check-square me-1"></i>
                                <u>My Todo-s</u>
                            </p>

                            <div class="pb-2">
                                <div class="card">
                                    <div class="card-body">
                                        <div class="d-flex flex-row align-items-center">
                                            <input type="text" v-model="newCourName"
                                                class="form-control form-control-lg" id="exampleFormControlInput1"
                                                placeholder="Add new...">
                                            <div class="author">
                                                <input type="text" v-model="newAuthorName"
                                                    class="form-control form-control-md" placeholder="Name Author">
                                                <input type="text" v-model="newAuthorLastname"
                                                    class="form-control form-control-md" placeholder="Lastname Author">
                                            </div>
                                            <div>
                                                <input type="checkbox" v-model="newCourEtat" class="m-4">
                                            </div>
                                            <div>
                                                <button type="button" @click="addCours" class="btn btn-primary">Add
                                                    cours</button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <hr class="my-4">

                            <ul v-for="item in reseveItems" :key="item.id"
                                class="list-group list-group-horizontal rounded-0 bg-transparent">
                                <li
                                    class="list-group-item d-flex align-items-center ps-0 pe-3 py-1 rounded-0 border-0 bg-transparent">
                                    <div class="form-check">
                                        <input class="form-check-input me-0" type="checkbox" value=""
                                            id="flexCheckChecked1" aria-label="..." :checked="item.isComplet" />
                                    </div>
                                </li>
                                <li
                                    class="list-group-item px-3 py-1 d-flex align-items-center flex-grow-1 border-0 bg-transparent">
                                    <p class="lead fw-normal mb-0">{{ item.cour }}</p>
                                </li>
                                <li
                                    class="list-group-item px-3 py-1 d-flex align-items-center flex-grow-1 border-0 bg-transparent">
                                    <small class=" ">{{ item.author.name  }} <em>{{item.author.lastname}}</em></small>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'ReactivityComponent',
    data() {
        return {
            title: 'Bienvenue',
            description: "  Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cumque neque eveniet nihil soluta aliquam quo veniam id. Delectus rerum quaerat quibusdam, similique consequatur corporis, neque repudiandae quos temporibus alias dolore?",
            items: [
                {
                    id: 1,
                    cour: 'Syntax',
                    isComplet: true,
                    author: {
                        name: 'John',
                        lastname: 'Doe'
                    }
                },
                {
                    id: 2,
                    cour: 'Template Syntax',
                    isComplet: true,
                    author: {
                        name: 'John',
                        lastname: 'Doe'
                    }
                },
                {
                    id: 3,
                    cour: 'Reactivityitem',
                    isComplet: false, author: {
                        name: 'John',
                        lastname: 'Doe'
                    }
                },
            ],
            newCourName: '',
            newCourEtat: false,
            newAuthorName: '',
            newAuthorLastname: ''
        }
    },
    methods: {
        addCours() {
            this.items.push({
                id: this.items.length + 1, cour: this.newCourName, isComplet: this.newCourEtat, author: {
                    name: this.newAuthorName,
                    lastname: this.newAuthorLastname
                }
            })
        }

    },
    computed: {
        reseveItems() {
            return [...this.items].reverse()
        },
        authorFullName: {
            get() {
                return this.newAuthorName + ' ' + this.newAuthorLastname
            },
            set(fullNameValue) {
                [this.newAuthorName, this.newAuthorLastname] = fullNameValue.split(' ')
            }
        }
    }
}
</script>