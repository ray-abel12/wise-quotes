<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row">
           <div class="col-sm-12 text-center"></div>
            <div class="alert alert-info">info:click on a quote to delete it</div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from "./component/QuoteGrid.vue";
    import NewQuote from "./component/NewQuote.vue";
    import Header from "./component/Header.vue";
    export default {
        data:function () {
            return{
                quotes:['just testing'],
                maxQuotes : 10
            }
        },
        components: {
            appQuoteGrid  :QuoteGrid,
            appNewQuote   :NewQuote,
            appHeader :Header
        },
        methods:{
            newQuote(quote){
                if(this.quotes.length >=this.maxQuotes){
                    return alert('please delete quote first');
                }
                this.quotes.push(quote)
            },
            deleteQuote(index){
                this.quote.slice(index,1);
            }
        }
    }
</script>

<style>
</style>
