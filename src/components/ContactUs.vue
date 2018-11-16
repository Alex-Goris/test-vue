<template>
    <div class="container contact-form mt-5">
        <form method="post">
            <h3>Contact Us</h3>
            <div class="row">
                <div class="col-md-6">
                    <div class="form-group">
                        <input type="text" name="txtName" readonly class="form-control" placeholder="Your Name *" value="" />
                    </div>

                    <div class="form-group">
                        <input type="text" name="txtPhone" class="form-control" placeholder="cdddd" value="+380" />

                    </div>
                    <div class="form-group">
                        <input type="submit" name="btnSubmit" class="btn btn-secondary btnContact" value="Send Message" />
                    </div>
                </div>
                <div class="col-md-6">
                    <div class="form-group">
                        <textarea name="txtMsg" class="form-control" placeholder="Your Message *" style="width: 100%; height: 150px;"></textarea>
                        <hr>
                        <h6 class="pull-right" id="count_message"></h6>
                    </div>
                </div>
            </div>
        </form>
    </div>
</template>